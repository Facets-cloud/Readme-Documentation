---
title: Redis memorystore flavor
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
This is the implementation to create an instance of memorystore database for GCP.

Terraform resources used:

* [google\_redis\_instance](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/redis_instance)

## JSON values

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Optional
      </th>

      <th>
        Type
      </th>

      <th>
        Values
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        `flavor`
      </td>

      <td>
        No
      </td>

      <td>
        string
      </td>

      <td>
        `memorystore`
      </td>
    </tr>

    <tr>
      <td>
        `kind`
      </td>

      <td>
        No
      </td>

      <td>
        string
      </td>

      <td>
        `redis`
      </td>
    </tr>

    <tr>
      <td>
        `version`
      </td>

      <td>
        No
      </td>

      <td>
        string
      </td>

      <td>
        `0.1`\
        Default value - `latest`.
      </td>
    </tr>

    <tr>
      <td>
        `disabled`
      </td>

      <td>
        Yes
      </td>

      <td>
        boolean
      </td>

      <td>
        `true`, `false`\
        Default value - `true`
      </td>
    </tr>

    <tr>
      <td>
        `provided`
      </td>

      <td>
        Yes
      </td>

      <td>
        boolean
      </td>

      <td>
        `true`, `false`\
        Default value - `false`
      </td>
    </tr>

    <tr>
      <td>
        `depends_on`
      </td>

      <td>
        Yes
      </td>

      <td>
        array
      </td>

      <td>
        Default value - `[]`
      </td>
    </tr>

    <tr>
      <td>
        `metadata`
      </td>

      <td>
        No
      </td>

      <td>
        object
      </td>

      <td>
        See [metadata](https://readme.facets.cloud/docs/redis-intent#metadata).
      </td>
    </tr>

    <tr>
      <td>
        `spec`
      </td>

      <td>
        No
      </td>

      <td>
        object
      </td>

      <td>
        See [spec](https://readme.facets.cloud/docs/redis-intent#spec).
      </td>
    </tr>

    <tr>
      <td>
        `out`
      </td>

      <td>
        Yes
      </td>

      <td>
        object
      </td>

      <td>
        See [out](https://readme.facets.cloud/docs/redis-intent#out).
      </td>
    </tr>
  </tbody>
</Table>

## Advanced Schema

[Redis Memorystore flavor schema ](https://github.com/Facets-cloud/facets-schemas/blob/master/schemas/redis/flavor-memorystore.schema.json)

### Advanced values

| Key                                 | Optional | Type | Description                                                                                                                                                   |
| :---------------------------------- | :------- | :--- | :------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `memorystore.google_redis_instance` | Yes      | Map  | Resource values as per the [terraform resource documentation](https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/redis_instance). |
