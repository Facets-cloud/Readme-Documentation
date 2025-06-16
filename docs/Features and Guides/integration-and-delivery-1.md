---
title: CI/CD
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
## Introduction

Facets is a powerful platform designed to streamline and automate the deployment of applications and services in the cloud. It encompasses various tools and processes to ensure smooth and efficient delivery cycles. Two fundamental components of this process are Continuous Integration (CI) and Continuous Deployment (CD).

## CI in Facets

Continuous Integration (CI) in Facets refers to the practice of automatically building, testing, and merging code changes into a shared repository. This helps in identifying issues early in the development process, improving code quality, and reducing integration problems. 

## CD in Facets

Continuous Deployment (CD) in Facets is the practice of automatically deploying code changes to production or other environments after they pass the CI pipeline. This ensures that new features, bug fixes, and improvements are delivered to users quickly and reliably.

## CI Integration

A CI Integration is an entity in Facets that provides a central repository for storing and managing Docker images for a service. Facets enables users to create CI Integration with support for multiple Container Registries, including AWS ECR and other platforms like ACR, GCR, Nexus, and Docker Hub.

## Facets CLI

Facets CLI is an easy-to-use alternative to Facets APIs that allows you to push new Docker artifacts to the Facets Control Plane, refresh Kubernetes credentials for the user in a specified environment, and many other useful functionalities.
