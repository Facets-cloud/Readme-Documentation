---
title: Redis
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Redis `intent `can be provisioned in the following flavors:

* [K8s](https://readme.facets.cloud/docs/redis-k8s-flavor)
* [Elasticache](https://readme.facets.cloud/docs/redis-elasticache-flavor)
* [Memorystore](https://readme.facets.cloud/docs/redis-memorystore-flavor)

# Base JSON values

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Key
      </th>

      <th style={{ textAlign: "left" }}>
        Optional
      </th>

      <th style={{ textAlign: "left" }}>
        Type
      </th>

      <th style={{ textAlign: "left" }}>
        Values
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        `flavor`
      </td>

      <td style={{ textAlign: "left" }}>
        No
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>

      <td style={{ textAlign: "left" }}>
        `k8s`, `elasticache`, `memorystore`
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        `kind`
      </td>

      <td style={{ textAlign: "left" }}>
        No
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>

      <td style={{ textAlign: "left" }}>
        `redis`
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        `version`
      </td>

      <td style={{ textAlign: "left" }}>
        No
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>

      <td style={{ textAlign: "left" }}>
        Any eligible version.\
        Default value - `latest`.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        `disabled`
      </td>

      <td style={{ textAlign: "left" }}>
        Yes
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>

      <td style={{ textAlign: "left" }}>
        `true`, `false`\
        Default value - `true`
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        `provided`
      </td>

      <td style={{ textAlign: "left" }}>
        Yes
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>

      <td style={{ textAlign: "left" }}>
        `true`, `false`\
        Default value - `false`
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        `depends_on`
      </td>

      <td style={{ textAlign: "left" }}>
        Yes
      </td>

      <td style={{ textAlign: "left" }}>
        array
      </td>

      <td style={{ textAlign: "left" }}>
        Default value - `[]`
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        `metadata`
      </td>

      <td style={{ textAlign: "left" }}>
        No
      </td>

      <td style={{ textAlign: "left" }}>
        object
      </td>

      <td style={{ textAlign: "left" }}>
        See [metadata](https://readme.facets.cloud/docs/redis-intent#metadata).
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        `spec`
      </td>

      <td style={{ textAlign: "left" }}>
        No
      </td>

      <td style={{ textAlign: "left" }}>
        object
      </td>

      <td style={{ textAlign: "left" }}>
        See [spec](https://readme.facets.cloud/docs/redis-intent#spec).
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        `out`
      </td>

      <td style={{ textAlign: "left" }}>
        Yes
      </td>

      <td style={{ textAlign: "left" }}>
        object
      </td>

      <td style={{ textAlign: "left" }}>
        See [out](https://readme.facets.cloud/docs/redis-intent#out).
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        `advanced`
      </td>

      <td style={{ textAlign: "left" }}>
        Yes
      </td>

      <td style={{ textAlign: "left" }}>
        object
      </td>

      <td style={{ textAlign: "left" }}>
        See [advanced](https://readme.facets.cloud/docs/redis-intent#advanced).
      </td>
    </tr>
  </tbody>
</Table>

## metadata

| Key    | Optional | Type   | Description                                                          |
| :----- | :------- | :----- | :------------------------------------------------------------------- |
| `name` | Yes      | string | Name of the resource. If not specified, fall back is the `filename`. |

## spec

| Key                   | Optional | Type                                                                    | Description                                |
| :-------------------- | :------- | :---------------------------------------------------------------------- | :----------------------------------------- |
| `authenticated`       | No       | boolean                                                                 | Flag to make this redis password protected |
| `redis_version`       | No       | string                                                                  | Version of redis e.g. 6.3                  |
| `persistence_enabled` | No       | boolean                                                                 | Flag to enable persistence for this redis. |
| `size`                | No       | [Reader-Writer](https://readme.facets.cloud/docs/modules#reader-writer) | Size of Reader-Writer.                     |

### Example spec JSON

```json
  "spec": {
    "authenticated": true,
    "redis_version": "6.2",
    "persistence_enabled": true,
    "size": {
      "writer": {
        "cpu": "1",
        "memory": "512M",
        "replica_count": 1
      },
      "reader": {
        "cpu": "1",
        "memory": "512M",
        "replica_count": 0
      }
    }
  }
```

## out

> ❗ NOTE
>
> The out trait references all properties of the spec trait.

| Key          | Optional | Type                                                                                        | Description                   |
| :----------- | :------- | :------------------------------------------------------------------------------------------ | :---------------------------- |
| `spec`       | Yes      | [Spec](https://readme.facets.cloud/docs/redis-intent#spec)                                  | Complete Spec of this module. |
| `interfaces` | Yes      | [Reader-Writer Interface](https://readme.facets.cloud/docs/modules#reader-writer-interface) | Master SD details.            |
| `instances`  | Yes      | Map\<string, [Interface](https://readme.facets.cloud/docs/modules#interface)>               | List of all instances.        |
