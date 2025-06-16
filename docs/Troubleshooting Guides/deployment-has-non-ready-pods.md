---
title: Deployment has Non-Ready Pods
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
This guide will help you to identify the issues related to non-ready pods.

### Example Alert

* `CRITICAL Alert: Deployment cloud-connect has non-ready pods for longer than a 15m.`
* `CRITICAL Alert: StatefuleSet chi-test-test-0-0 has non-ready pods for longer than a 15m.`

## How to Identify the Issue?

If you receive an alert indicating that there are non-ready pods, follow these steps to identify the problem:

1. **Locate the Deployment Name:**\
   The alert will contain the deployment name, which will help you identify the pod name. Refer to [this section](doc:deployment-has-non-ready-pods#how-to-get-the-pod-name) to know how to get the pod name. 
2. **Describe the Pod:**\
   Use the following command to describe the pod and find the issue under the **Events** section:

```Text SHELL
kubectl describe pod <podname> -n <namespace>
```

Once you identified the issue, you can further debug and find a solution.

## How to Get the Pod Name?

To retrieve the pod name, follow these steps:

1. **Download Kubernetes Credentials:**\
   Navigate to the Environment **Overview** tab and click **K8s Credentials** to download the Kubernetes credentials.
2. **Export the Kubernetes Configuration:**\
   Use the following command to export the kubeconfig:

```Text SHELL
export KUBECONFIG=~/path/to/<kubeconfig>
```

3. **Retrieve the Pod Name:**\
   Run the following command to get the list of pods and identify the pod associated with the deployment name:

```Text SHELL
kubectl get pods -n <namespace> | grep -i <deployment-name/statefulset-name>
```

After retrieving the pod name, refer to [this section](doc:deployment-has-non-ready-pods#how-to-identify-the-issue) to describe the pod and identify the issue.
