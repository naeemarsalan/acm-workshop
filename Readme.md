# ACM Hands-On Workshop

## Overview
Welcome to the **ACM Hands-On Workshop**! This session will guide you through the process of deploying and monitoring a microservices application using a structured pipeline approach. You will gain hands-on experience with pipeline deployment, monitoring, ACM integration, drift management, and policy validation.

## Workshop Objectives
By the end of this workshop, you will have accomplished the following:

- **Deploy Bookinfo App:** Deploy a real-world microservices application.
- **Pipeline Deployment:** Set up a pipeline to monitor workload health.
- **Create Monitoring Pipelines:**
  - Ensure the health of the Bookinfo application.
  - Verify that `ClusterLogForwarder` exists for container logs.
- **ACM Integration:** Utilize ACM (Advanced Cluster Management) to streamline deployment and enforce consistency.
- **Drift Management:** Implement strategies to detect and correct configuration drift.
- **Policy Validation:** Define and enforce policies to ensure pipeline and infrastructure consistency.

## Prerequisites
Before starting, ensure you have:
- Access to a **development Openshift cluster**.
- Installed **oc**, **tkn**, **git** 

## Workshop Walkthrough
### 1. Deploy Bookinfo Application
- Deploy the **Bookinfo** application into your development cluster using the CLI within your assigned project.

### 2. Develop Pipeline 
- Learn to create pipeline, how pipelines work. 

### 3. Deploy Bookinfo/Pipeline via ArgoCD
- Deploy bookinfo pipeline using **ArgoCD** into the dev cluster.

### 4. Policy Creation
- **Namespace Policy:** Ensure that the expected namespace exists.
- **Pipeline Policy:** Validate that the required pipeline is deployed and functional.

## Summary
This workshop provides practical insights into deploying microservices, monitoring workloads, and managing infrastructure consistency using ACM and ArgoCD. By following these steps, you will gain hands-on experience with real-world deployment and policy enforcement techniques.

Happy coding! 🚀


