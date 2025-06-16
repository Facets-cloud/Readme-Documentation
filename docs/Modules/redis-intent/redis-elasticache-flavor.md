---
title: Redis elasticache flavor
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
This is the implementation to create an Elasticache database with cluster mode disabled.

Terraform resources used:

* [aws\_elasticache\_replication\_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_replication_group)
* [aws\_elasticache\_parameter\_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_parameter_group)
* [aws\_security\_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)
* [aws\_elasticache\_subnet\_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_subnet_group)

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
        `elasticache`
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

[Redis elasticache flavor schema](https://facets-cloud.github.io/facets-schemas/schemas/redis/flavor-elasticache.schema.json)

### Advanced values

| Key                                             | Optional | Type | Description                                                                                                                                                                                                                                                           |
| :---------------------------------------------- | :------- | :--- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `elasticache.aws_elasticache_replication_group` | Yes      | Map  | Cluster values for this resource as per the [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache\_replication\_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_replication_group). |
| `elasticache.aws_elasticache_parameter_group`   | Yes      | Map  | Parameter group values for this resource as per the [elasticache\_parameter\_group documentation](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_parameter_group).                                                           |
| `elasticache.aws_security_group`                | Yes      | Map  | Security group values for this resource as per the [security\_group documentation](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group).                                                                                       |
