---
title: Handle Log Collector Alerts
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
This guide covers how to handle alerts related to Loki's components, including CPU and memory throttling and OOM (Out of Memory) killed issues.

## Promtail - CPU Throttling

If you receive a CPU throttling alert for Promtail, follow these steps to increase the CPU limits:

1. Open the **Projects** tab and select the required project
2. In the **Environments** tab, select the required Environment.  
3. Now, in the **Resource Center** tab, select the appropriate `log_collector` resource. 
4. Under the **Spec Overrides** tab, click **Edit.**
5. To increase the CPU, update the CPU limits at the specified JSON path by referring to the [Helm chart.](https://artifacthub.io/packages/helm/grafana/promtail?modal=values&path=resources)

The following is the JSON path to increase CPU limits:

```Text JSON
advanced.<flavor>.promtail.values.resources.limits.cpu 
```

```Text Example
{
  "advanced": {
    "loki_s3": {
      "loki": {
        "values": {
          "ingester": {
            "resources": {
              "limits": {
                "memory": "700Mi"
              }
            }
          }
        }
      }
    }
  }
}
```

6. After updating the CPU limits, perform a release to apply the changes.
7. Monitor the alerts to ensure there are no further occurrences of CPU throttling alerts for Promtail.

## Promtail - Memory Throttling

If you receive a memory throttling alert for Promtail, follow these steps to increase the memory limits:

1. Open the **Projects** tab and select the required project
2. In the **Environments** tab, select the required Environment.  
3. Now, in the **Resource Center** tab, select the appropriate `log_collector` resource. 
4. Under the **Spec Overrides** tab, click **Edit.**
5. To increase the memory, update the memory limits at the specified JSON path by referring to the [Helm chart.](https://artifacthub.io/packages/helm/grafana/promtail?modal=values&path=resources)

The following is the JSON path to increase memory limits:

```Text JSON
advanced.<flavor>.promtail.values.resources.limits.memory
```

```Text Example
{
  "advanced": {
    "<loki|loki_s3|loki_blob|loki_gcs>": {
      "promtail": {
        "values": {
          "resources": {
            "limits": {
              "memory": "500m"
            }
          }
        }
      }
    }
  }
}
```

6. After updating the memory limits, perform a release to apply the changes.
7. Monitor the alerts to ensure there are no further occurrences of memory throttling alerts for Promtail.

## Loki Component - CPU Throttling

If you receive a CPU throttling alert for any of Loki's components, follow these steps to increase the CPU limits.

1. Open the **Projects** tab and select the required project
2. In the **Environments** tab, select the required Environment.  
3. Now, in the **Resource Center** tab, select the appropriate `log_collector` resource. 
4. Under the **Spec Overrides** tab, click **Edit.**
5. To increase the CPU for affected components, update the CPU limits at the specified JSON path by referring to the [Helm chart.](https://artifacthub.io/packages/helm/grafana/loki-distributed?modal=values)

The following is the JSON path to increase CPU limits:

```Text JSON
advanced.<flavor>.loki.values.<component>.resources.limits.cpu  
```

Example JSON to increase CPU for the ingester component:

```Text Example
{
  "advanced": {
    "<loki|loki_s3|loki_blob|loki_gcs>": {
      "loki": {
        "values": {
          "ingester": {
            "resources": {
              "limits": {
                "cpu": "500m"
              }
            }
          }
        }
      }
    }
  }
}
```

6. After updating the CPU limits, perform a release to apply the changes.
7. Monitor the alerts to ensure there are no further occurrences of CPU throttling alerts for Loki's components.

## Loki Component - Memory Throttling

If you receive a memory throttling alert for any of Loki's components, follow these steps to increase the memory limits.

1. Open the **Projects** tab and select the required project
2. In the **Environments** tab, select the required Environment.  
3. Now, in the **Resource Center** tab, select the appropriate `log_collector` resource. 
4. Under the **Spec Overrides** tab, click **Edit.**
5. To increase the memory for affected components, update the memory limits at the specified JSON path by referring to the [Helm chart.](https://artifacthub.io/packages/helm/grafana/loki-distributed?modal=values)

```Text JSON
advanced.<flavor>.loki.values.<component>.resources.limits.memory
```

Example JSON to increase memory for the ingester component:

```Text Example
{  
  "advanced": {  
    "<loki|loki_s3|loki_blob|loki_gcs>": {  
      "loki": {  
        "values": {  
          "ingester": {  
            "resources": {  
              "limits": {  
                "memory": "500Mi"  
              }  
            }  
          }  
        }  
      }  
    }  
  }  
}
```

6. After updating the memory limits, perform a release to apply the changes.
7. Monitor the alerts to ensure there are no further occurrences of memory throttling alerts for Loki's components.

## Loki - OOM Killed

If you encounter a query error with a read timeout, 

1. Verify the status of the components using the following command:
   ```Text SHELL
   kubectl get pod -n facets
   ```
2. If the status is reported as `CrashLoopBackOff` or if you observe frequent restarts of components it is necessary to investigate the cause for the restarts.  
   The following command can be used to retrieve the reason for the last termination :

```Text SHELL
kubectl -n facets get pod <pod-name> -o go-template='{{range .status.containerStatuses}}{{printf "%s:\n%s\n\n" .name .lastState.terminated.reason}}{{end}}'
```

If the reason for termination is OOMKilled, follow these steps to increase the memory:

1. Open the **Projects** tab and select the required project
2. In the **Environments** tab, select the required Environment.  
3. Now, in the **Resource Center** tab, select the appropriate `log_collector` resource. 
4. Under the **Spec Overrides** tab, click **Edit.**
5. To increase the memory for affected components, update the memory limits at the specified JSON path by referring to the [Helm chart.](https://artifacthub.io/packages/helm/grafana/loki-distributed?modal=values)

JSON path to increase memory limits:

```Text JSON
advanced.<flavor>.loki.values.<component>.resources.limits.memory
```

Example JSON to increase memory for the ingester component:

```Text Example
{  
  "advanced": {  
    "<loki|loki_s3|loki_blob|loki_gcs>": {  
      "loki": {  
        "values": {  
          "ingester": {  
            "resources": {  
              "limits": {  
                "memory": "700Mi"  
              }  
            }  
          }  
        }  
      }  
    }  
  }  
}
```

6. After updating the memory limits, perform a release to apply the changes.
7. Monitor the components to ensure there are no further occurrences of OOMKilled or CrashLoopBackOff status.