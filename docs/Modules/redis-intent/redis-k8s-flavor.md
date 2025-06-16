---
title: Redis k8s flavor
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
This flavor is a helm implementation to run Redis in k8s.

* Helm: [Bitnami Redis](https://github.com/bitnami/charts/tree/master/bitnami/redis)
* Version: 17.0.11

## JSON values

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
        `k8s`
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
        `0.1`\
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
  </tbody>
</Table>

## Advanced Schema

[Redis elasticache flavor schema](https://facets-cloud.github.io/facets-schemas/schemas/redis/flavor-elasticache.schema.json)

### Advanced values

| Key                | Optional | Type | Description                                                                                               |
| :----------------- | :------- | :--- | :-------------------------------------------------------------------------------------------------------- |
| `k8s.redis.values` | Yes      | Map  | Helm values as per the [Bitnami Redis chart](https://github.com/bitnami/charts/tree/master/bitnami/redis) |
