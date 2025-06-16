---
title: Supported Services in Cloud
fullscreen: false
hidden: true
metadata:
  title: ''
  description: ''
---
## Kubernetes (AWS, Azure & GCP)

* [Reddis](https://facets-cloud.github.io/facets-schemas/schemas/redis/redis.k8s.sample.json)
* [RabbitMQ](https://facets-cloud.github.io/facets-schemas/schemas/rabbitmq/rabbitmq.k8s.sample.json)
* [Mongo](https://facets-cloud.github.io/facets-schemas/schemas/mongo/mongo.k8s.sample.json)
* [Zookeeper](https://facets-cloud.github.io/facets-schemas/schemas/zookeeper/zookeeper.k8s.sample.json)
* [Kafka](https://facets-cloud.github.io/facets-schemas/schemas/kafka/kafka.k8s.sample.json)
* [Elasticsearch](https://facets-cloud.github.io/facets-schemas/schemas/elasticsearch/elasticsearch.k8s.sample.json)
* [ConfigMaps](https://facets-cloud.github.io/facets-schemas/schemas/config_map/config_map.k8s.sample.json)

***

## AWS

* Redis - [Elasticache](https://facets-cloud.github.io/facets-schemas/schemas/redis/redis.elasticache.sample.json)
* kubernetes\_node\_pool - [eks\_managed](https://facets-cloud.github.io/facets-schemas/schemas/nodepool/nodepool.eks_managed.sample.json)
* kubernetes\_node\_pool - [eks\_self\_managed](https://facets-cloud.github.io/facets-schemas/schemas/nodepool/nodepool.eks_self_managed.sample.json)
* log\_collector - [Loki S3](https://facets-cloud.github.io/facets-schemas/schemas/log_collector/log_collector.loki_s3.sample.json)
* MySQL - [RDS](https://facets-cloud.github.io/facets-schemas/schemas/mysql/mysql.rds.sample.json)
* MySQL - [Aurora](https://facets-cloud.github.io/facets-schemas/schemas/mysql/mysql.aurora.sample.json)
* Service - [Default](https://facets-cloud.github.io/facets-schemas/schemas/service/service.default.sample.json)
* DynamoDb - [Default](https://facets-cloud.github.io/facets-schemas/schemas/dynamodb/dynamodb.default.sample.json)
* Ingress - [aws\_alb](https://facets-cloud.github.io/facets-schemas/schemas/loadbalancer/loadbalancer.alb.sample.json)
* Ingress - [aws\_alb](https://facets-cloud.github.io/facets-schemas/schemas/loadbalancer/ingress.aws_alb.sample.json)
* Peering - [Default](https://facets-cloud.github.io/facets-schemas/schemas/peering/peering.default.sample.json)
* Postgres - [Aurora](https://facets-cloud.github.io/facets-schemas/schemas/postgres/postgres.aurora.sample.json)
* iam\_policy - [aws\_iam\_policy](https://facets-cloud.github.io/facets-schemas/schemas/iam_policy/iam_policy.aws_iam_policy.sample.json)
* SQS - [Default](https://facets-cloud.github.io/facets-schemas/schemas/sqs/sqs.default.sample.json)
* S3 - [Default](https://facets-cloud.github.io/facets-schemas/schemas/s3/s3.default.sample.json)

***

## Azure

* kubernetes\_node\_pool - [aks](https://facets-cloud.github.io/facets-schemas/schemas/nodepool/nodepool.aks.sample.json)
* log\_collector - [loki\_blob](https://facets-cloud.github.io/facets-schemas/schemas/log_collector/log_collector.loki_blob.sample.json)
* MySQL - [flexible\_server](https://facets-cloud.github.io/facets-schemas/schemas/mysql/mysql.flexible_server.sample.json)
* Service - [Default](https://facets-cloud.github.io/facets-schemas/schemas/service/service.default.sample.json)
* Ingress - [alb](https://facets-cloud.github.io/facets-schemas/schemas/loadbalancer/ingress.nlb_nginx.sample.json)
* azure\_storage\_container - [Default](https://facets-cloud.github.io/facets-schemas/schemas/azure_storage_container/azure_storage_container.default.sample.json)

***

## GCP

* Redis - [memorystore](https://facets-cloud.github.io/facets-schemas/schemas/redis/redis.memorystore.sample.json)
* kubernetes\_node\_pool - [gke\_node\_pool](https://facets-cloud.github.io/facets-schemas/schemas/nodepool/nodepool.gke_node_pool.sample.json)
* MySQL - [CloudSQL](https://facets-cloud.github.io/facets-schemas/schemas/mysql/mysql.cloudsql.sample.json)
* Service - [Default](https://facets-cloud.github.io/facets-schemas/schemas/service/service.default.sample.json)
* Ingress - [gcp\_alb](https://facets-cloud.github.io/facets-schemas/schemas/loadbalancer/loadbalancer.gcp_alb.sample.json)
* Ingress - [alb, gcp\_alb](https://facets-cloud.github.io/facets-schemas/schemas/loadbalancer/ingress.alb.sample.json)
* Postgres - [cloudsql\_postgres](https://facets-cloud.github.io/facets-schemas/schemas/postgres/postgres.cloudsql_postgres.sample.json)
* Postgres - [cloudsql](https://facets-cloud.github.io/facets-schemas/schemas/postgres/postgres.cloudsql.sample.json)

***

## AWS, Azure & GCP

* Helm - [helm\_simple](https://facets-cloud.github.io/facets-schemas/schemas/helm/helm.helm_simple.sample.json)
* schemahero\_table - [Default](https://facets-cloud.github.io/facets-schemas/schemas/schemahero_table/schemahero_table.default.sample.json)
* log\_collector - [Loki](https://facets-cloud.github.io/facets-schemas/schemas/log_collector/log_collector.loki.sample.json)
* schemahero\_database - [Default](https://facets-cloud.github.io/facets-schemas/schemas/schemahero_database/schemahero_database.default.sample.json)
* alert\_group - [Default](https://facets-cloud.github.io/facets-schemas/schemas/alert_group/alert_group.default.sample.json)
* k8s\_resource - [Default](https://facets-cloud.github.io/facets-schemas/schemas/k8s_resource/k8s_resource.default.sample.json)
* grafana\_dashboard - [Default](https://facets-cloud.github.io/facets-schemas/schemas/grafana_dashboard/grafana_dashboard.default.sample.json)
* Ingress - [nlb\_nginx](https://facets-cloud.github.io/facets-schemas/schemas/loadbalancer/ingress.nlb_nginx.sample.json)
* snapshot\_schedule - [Default](https://facets-cloud.github.io/facets-schemas/schemas/snapshot_schedule/snapshot_schedule.default.sample.json)
* tcp\_lb - [nlb](https://facets-cloud.github.io/facets-schemas/schemas/tcp_lb/tcp_lb.nlb.sample.json)
* postgres\_user - [Default](https://facets-cloud.github.io/facets-schemas/schemas/postgres_user/postgres_user.default.sample.json)
* mysql\_user - [Default](https://facets-cloud.github.io/facets-schemas/schemas/mysql_user/mysql_user.default.sample.json)

***
