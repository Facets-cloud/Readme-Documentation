---
title: Viewing Kubernetes events
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
Facets Control Plane enables users to view Kubernetes Events in the Grafana Dashboard and filter them on the basis of namespace, kind, and name of the object.

The primary use case for this dashboard is to allow users to view the health of an application running inside a Kubernetes cluster directly from the Control Plane.

## How to View the Kubernetes Events?

1. Select the desired Blueprint from **Blueprints.**
2. Select the **Environment** tab and select the environment where you want to view the persistent dashboard.
3. Now, select the **Tools** tab from the top bar and select the **Grafana** tab.
4. Click on the **Search** button, search for the **Kubernetes Events** dashboard in the search menu, and open the same.
5. Choose the appropriate values for **ObjectKind**, **ObjectName**, **ObjectNamespace** fields.
6. You can now view the Events in a tabular format.
