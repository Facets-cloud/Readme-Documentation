---
title: Jenkins Post-build Step to push an Image to Facets Control Plane Automatically
description: Recipe Description
hidden: false
recipe:
  color: '#018FF4'
  icon: 🦉
---
```shell Shell
#!/bin/bash
set -e

BLUEPRINT_NAME=springbootsample
APPLICATION_NAME=$JOB_NAME
RELEASE_STREAM=QA2

BUILD_ARTIFACT=$ECR_REPO/ops/$APPLICATION_NAME:master-$BUILD_NUMBER
BUILD_ID=jenkins-$BUILD_NUMBER
docker build -t $BUILD_ARTIFACT 

#Refer to https://readme.facets.cloud/docs/command-line-tool-for-facets#commands
facetsctl login --username <value> --access-token <value> --cp-url <value>
facetsctl push --docker-image <value> --artifact-name <value> --registration-type CLUSTER|RELEASE_STREAM --registration-value
    <value> --external-id <value> [--description <value>] [--artifactory <value>]
```

# Set Environment Variables specific to the Blueprint

<!-- shell@1-6 -->

Assuming Application Name defined in the blueprint as JOB_NAME variable of Jenkins. However, it can be any value that you defined in the blueprint for this service

# Push the Docker Image to your Docker Repo

<!-- shell@8-11 -->

This is just an example. You would already be using a section similar to it

# Push the same artifact to Facets IDP

<!-- shell@13-15 -->

