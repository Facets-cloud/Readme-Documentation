---
title: Push a Build to Facets Control Plane Manually
description: Build and Push a docker image to Facets artifactory
hidden: false
recipe:
  color: '#802f9d'
  icon: ✈️
---
```shell Shell
git clone https://github.com/dstar55/docker-hello-world-spring-boot .
docker build -t="hello-world-java" .
docker run -p 8080:8080 -it --rm hello-world-java
curl localhost:8080
facetsctl-os configure <<CP_URL>> <<USER_NAME>> <<USER_TOKEN>>
facetsctl-os image push springbootsample springboot-backend QA2 hello-world-java:latest 123
```

```json Response Example
Hello World
```

# Checkout the code

<!-- shell@1 -->



# Build, Run and Test docker image

<!-- shell@2-4 -->



# Configure and Push image Image

<!-- shell@5-6 -->

Push the image to facets artifactory