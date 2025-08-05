---
title: Kubernetes AI Agent
deprecated: false
hidden: false
metadata:
  robots: index
---
## 1. Overview

**What it is**\
The Facets Kubernetes AI Agent is a built-in assistant that provides a natural language interface to interact with your Kubernetes clusters. It is integrated directly into the Facets platform, allowing engineers to query, troubleshoot, and manage cluster resources without needing to manually run `kubectl` commands.

**Key Benefits**

* **Accelerated Troubleshooting:** Quickly diagnose issues like pod crashes, resource bottlenecks, and network problems by asking direct questions.
* **Simplified Resource Analysis:** Get plain-language summaries of resource utilization (CPU, memory), deployments, and service statuses.
* **Increased Efficiency:** Reduce the time spent on routine Kubernetes information retrieval and debugging tasks, freeing up engineering resources for core development.

**Where to Access:**\
The agent is accessible within the Facets platform. Navigate to your desired environment's overview page, check the "Kubernetes Cluster" card, and click on the "Ask AI" button on the card.

## 2. Capabilities

The agent can perform a wide range of read-only and analytical tasks on your cluster, leveraging the permissions granted by your kubeconfig.

* **Resource Inspection:** Get details on pods, deployments, services, nodes, namespaces, and other Kubernetes objects.
* **Log Analysis:** Fetch and search logs from specific pods or containers.
* **Event-Based Debugging:** Analyze Kubernetes events to understand the root cause of failures (e.g., pod eviction, image pull errors).
* **Resource Usage Monitoring:** Report on CPU and memory requests, limits, and actual usage across various scopes (pod, namespace, node).
* **Health Checks:** Summarize the status and health of deployments, pods, and services.
* **Network Troubleshooting:** Inspect service endpoints, ingress rules, and network policies.

## 3. How to Use It

1. **Open the Agent:** Navigate to the Kubernetes section of your environment and open the AI Assistant.
2. **Select Context:** The agent automatically uses the Kubernetes context associated with the current Facets environment.
3. **Enter a Prompt:** Type your question or command in plain English into the input box.
4. **Review the Response:** The agent will process your request and return the output, which may include formatted text, tables, or log snippets.

<Embed typeOfEmbed="jsfiddle" url="https://app.storylane.io/demo/thldbtpl7fzd" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fthldbtpl7fzd%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fthldbtpl7fzd%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_23247888-d800-44c2-84e4-7bce5bc1530b%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22449%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" href="https://app.storylane.io/demo/thldbtpl7fzd" providerUrl="https://www.storylane.io" providerName="Storylane" />

<br />

## 4. How It Works

The AI Agent acts as an intelligent layer between you and the Kubernetes API server.

* **Kubeconfig Integration:** The agent uses the same kubeconfig credentials that you have configured for the Facets platform to connect to your cluster. It does not store or require separate credentials.
* **Secure API Interaction:** When you enter a prompt, the agent interprets your intent and translates it into one or more secure, read-only Kubernetes API calls.
* **RBAC and Scoped Access:** All interactions are governed by the Role-Based Access Control (RBAC) policies defined in your cluster. The agent's capabilities are strictly limited to the permissions of the user account or service account specified in your kubeconfig. It cannot perform actions that you are not authorized to perform.

## 5. Example Prompts

**Debugging:**

* "Why is the pod 'frontend-xyz-12345' in the 'production' namespace crash-looping?"
* "Show me the recent events for the 'database-main' deployment."
* "Get the last 100 lines of logs from the 'api-gateway' container in pod 'gateway-abc-67890'."

**Information Retrieval:**

* "List all pods in the 'staging' namespace with the label 'app=backend'."
* "Describe the service 'user-service-prod'."
* "Show me the CPU and memory usage for all nodes."
* "What are the ingress rules for the hostname 'api.example.com'?"

## 6. Access Control

Security is paramount. The agent's access is strictly controlled and audited.

* **Role-Based Access Control (RBAC):** The agent's actions are 100% constrained by the RBAC permissions of the user's kubeconfig. If a user has read-only access to the default namespace, the agent can only perform read-only actions within that namespace on their behalf.
* **Scoped Permissions:** Access is limited to the scope defined in the kubeconfig. The agent cannot see or interact with clusters or resources outside of this scope.

## 7. Secrets and ConfigMaps

The agent is designed to handle sensitive information securely.

* **Kubeconfig Security:** Your kubeconfig file is stored encrypted at rest within the Facets platform's secure storage.
* **Access to Secrets Based on Permissions:** The agent can access Kubernetes Secrets that the user has permissions to view, as defined by the RBAC policies associated with the kubeconfig credentials.

## 8. Compliance and Legal

The AI Agent is developed in accordance with industry-standard security and data privacy practices.

* **Data Handling:** The agent processes queries in-memory and does not store the content of your cluster's resources. Prompts and responses may be logged for auditing and improvement purposes, but will not contain sensitive data from your cluster.
* **Terms of Use:** Usage of the AI Agent is covered under the Facets Platform Terms of Use.

## 9. Troubleshooting & FAQ

**Q: What happens if the AI can't answer a question?**\
A: The agent may respond that it cannot fulfill the request. This can happen if the question is ambiguous, outside its capabilities, or if it lacks the necessary permissions to retrieve the information. Try rephrasing the question to be more specific.

**Q: What does an "insufficient permissions" error mean?**\
A: This means the user account or service account defined in your kubeconfig does not have the required RBAC permissions in Kubernetes to perform the action the agent attempted. For example, to view logs, your role needs `get` and `list` permissions on pods and the `logs` sub-resource.