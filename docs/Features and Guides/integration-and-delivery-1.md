---
title: CI/CD in Facets
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
## Introduction

Facets is designed to streamline and automate the deployment of applications and services in the cloud. Two fundamental components of this process are Continuous Integration (CI) and Continuous Deployment (CD).

While traditional CI/CD focuses on automating the build, test, and deployment pipeline, Facets extends this concept by adding environment management, infrastructure automation, and sophisticated promotion strategies.

## Traditional CI/CD vs Facets Approach

### Traditional CI/CD Challenges

* Multiple tool configurations for different environments and complex branch management for different deployment stages
* Manual tracking of image versions across environments and complicated promotion processes between environments
* Inconsistent deployment strategies across services

### Facets Solution

* Centralised project-level CD flow configuration and automated branch-to-environment mapping
* Built-in promotion workflows and consistent deployment strategies across service
* Flexible image management options

***

## Key Components

### 1. Project-Level CD Flow

Define deployment strategies at the project level that can be used across all services:

* Branch-to-environment mapping rules and/or
* Promotion workflows

### 2. Service-Level Implementation

Choose how each service implements the project's CD flow:

* Automatic image registration from CI pipelines
* Manual promotion between environments
* Manual/Automatic release once image is registered in the respective environments.

Lets look into each section in detail.
