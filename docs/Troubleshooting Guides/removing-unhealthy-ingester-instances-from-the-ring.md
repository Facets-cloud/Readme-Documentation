---
title: Removing Unhealthy Ingester Instances from the Ring
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
While fetching logs from the Grafana UI, if you encounter an error indicating an excess of unhealthy instances in the ring, please adhere to the following steps to rectify the issue:

## How to remove unhealthy Ingester instances from the Ring?

1. The first step is to [download](https://readme.facets.cloud/page/downloading-the-kubeconfig-file) the kubeconfig file.

2. Next, export the credentials using the below command:

   ```
      export KUBECONFIG=<PATH TO YOUR KUBECONFIG> 
   ```

3. Proceed to get the Ingester Service using the following command:

   ```
       kubectl get service -n facets 
   ```

4. Now, port forward the Ingester Service using the following command:

   ```
       kubectl port-forward svc/facets-loki-loki-distributed-ingester -n facets 3100:3100
   ```

5. Open your browser and access the UI at [localhost:3100/ring.](localhost:3100/ring) 

6. Here, you will be able to view the unhealthy instances.

7. Click **Forget** beside the unhealthy instance to remove it.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d70109a-image.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]