---
title: Setting up Loki to fetch logs from VM's
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
To set up Loki to fetch logs from applications running on AWS EC2 instances, you need to [add](doc:adding-resources) a `k8s_resource` to your Blueprint to deploy an internal load balancer. After that, install and configure Promtail on your VM.

**Note:** This guide assumes Loki is already deployed and running in your environment. If not, please follow the [Enable Loki](https://doc.clickup.com/3443930/p/h/3936u-49324/be9c419e59e515e) runbook to deploy Loki.

## How to Add a K8s Resource to the Blueprint?

To deploy an internal load balancer, you need a K8s resource.

1. Navigate to the **Blueprint** and click **Add Resource.** Search for and add **K8s Resource.**
2. Now, select the resource and click **Configure.**
3. In the JSON mode, replace the current contents with the contents given below.

```
{
	"flavor": "default",
	"metadata": {
		"name": "log-collector-lb-svc",
		"namespace": "facets"
	},
	"advanced": {
		"k8s_resource": {}
	},
	"kind": "k8s_resource",
	"disabled": true,
	"version": "latest",
	"spec": {
		"resource": {
			"apiVersion": "v1",
			"kind": "Service",
			"metadata": {
				"name": "log-collector-lb-svc",
				"namespace": "facets",
				"annotations": {
					"service.beta.kubernetes.io/aws-load-balancer-type": "elb",
					"service.beta.kubernetes.io/aws-load-balancer-internal": "true",
					"service.beta.kubernetes.io/aws-load-balancer-scheme": "internal",
					"service.beta.kubernetes.io/aws-load-balancer-nlb-target-type": "ip"
				}
			},
			"spec": {
				"type": "LoadBalancer",
				"ports": [
					{
						"name": "http",
						"protocol": "TCP",
						"targetPort": "http",
						"port": 80
					}
				],
				"selector": {
					"app.kubernetes.io/component": "gateway",
					"app.kubernetes.io/instance": `<loki-instance-name>`,
					"app.kubernetes.io/name": "loki-distributed"
				}
			}
		}
	}
}
```

4. Replace `<loki-instance-name>` with the instance name of the Loki provisioned via the Blueprint.

## Installing Promtail on Your VM

1. To forward logs to your Loki setup, you need to install Promtail on your VM.
2. To download and Install Promtail, run the following commands on your VM:

```
mkdir /opt/promtail && cd /opt/promtail
curl -O -L "https://github.com/grafana/loki/releases/download/v1.5.0/promtail-linux-amd64.zip"
unzip "promtail-linux-amd64.zip"
chmod a+x "promtail-linux-amd64"
```

**Note:** The commands may vary depending on the base image of your virtual machine. Please refer to the [official documentation](https://grafana.com/docs/loki/latest/send-data/promtail/installation/) for deploying Promtail.

## Creating the configuration file

To set up Promtail on the VM, create the configuration file and run Promtail with those configurations.

Create the following configuration file, replacing `<loki-internal-dns>` with the DNS name of the load balancer created by deploying the k8s\_resource. 

Modify other parameters according to your service configuration, especially the scrape\_configs section to specify the targets and paths to the log files.

```
server:
  http_listen_port: 9080
  grpc_listen_port: 0

positions:
  filename: /tmp/positions.yaml

client:
  url: http://<loki-internal-dns>/api/prom/push

scrape_configs:
 - job_name: system
   pipeline_stages:
   - docker:
   static_configs:
   - targets:
      - localhost
     labels:
      job: varlogs
      host: yourhost
      __path__: /var/log/*.log

 - job_name: someone_service
   pipeline_stages:
   - docker:
   static_configs:
   - targets:
      - localhost
     labels:
      job: someone_service
      host: yourhost
      __path__: /srv/log/someone_service/*.log

```

Save this file on your VM as `./ec2-promtail.yaml`. This file will be required to run Promtail.

## Running Promtail on Your VM as a Daemon

Create a new service to run Promtail as a daemon by using the following steps:

1. Create the Service Definition:

   1. Create a new service using `vim /etc/systemd/system/promtail.service`.
   2. Copy and paste the following service definition:

   ```
   [Unit]
   Description=Promtail

   [Service]
   User=root
   WorkingDirectory=/opt/promtail/
   ExecStartPre=/bin/sleep 30
   ExecStart=/opt/promtail/promtail-linux-amd64 --config.file=./ec2-promtail.yaml
   SuccessExitStatus=143
   TimeoutStopSec=10
   Restart=on-failure
   RestartSec=5

   [Install]
   WantedBy=multi-user.target

   ```
2. Reload systemd, enable, and start the Promtail service:
   ```
   systemctl daemon-reload
   systemctl enable promtail.service
   systemctl start promtail.service
   ```
3. Verify the Service:
   1. Ensure the service is running correctly by using the following command:
      ```
      systemctl status promtail.service -l
      ```

By following these steps, you should start seeing application logs available on Loki.