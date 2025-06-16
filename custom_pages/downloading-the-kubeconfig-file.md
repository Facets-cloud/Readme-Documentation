---
title: Downloading the kubeconfig file
fullscreen: false
hidden: true
metadata:
  title: ''
  description: ''
---
You can follow these links to learn how to access the kubeconfig file of your cluster based on the cloud service you are using:

- [Amazon Web Services (AWS)](https://docs.aws.amazon.com/eks/latest/userguide/create-kubeconfig.html)
- [Google Cloud Platform (GCP)](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl)
- [Microsoft Azure](https://learn.microsoft.com/en-us/azure/aks/control-kubeconfig-access#get-and-verify-the-configuration-information)

### sample kubeconfig file

```
apiVersion: v1  
clusters:
- cluster:  
      certificate-authority-data: ${cluster_ca_certificate} //Use this value for CERTIFICATE AUTHORITY
      server: ${endpoint} //Use this value for HOST  
    name: ${cluster_name}  
  contexts:
- context:  
      cluster: ${cluster_name}   
      user: ${user_name}  
    name: ${name}  
  current-context: your-context  
  kind: Config  
  preferences: {}  
  users:
- name: ${name}  
  user:  
    token: ${access_token} //Use this value for TOKEN
```