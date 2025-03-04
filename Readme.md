# ACM Hands-On Workshop

## Overview
Welcome to the **ACM Hands-On Workshop**! This session will guide you through the process of deploying and monitoring a microservices application using a structured pipeline approach. You will gain hands-on experience with pipeline deployment, monitoring, ACM integration, drift management, and policy validation.

## Workshop Objectives
By the end of this workshop, you will have accomplished the following:

- **Pipeline Deployment:** Set up a pipeline to monitor workload health.
- **Deploy Bookinfo App:** Deploy a real-world microservices application.
- **Create Monitoring Pipelines:**
  - Ensure the health of the Bookinfo application.
  - Verify that `ClusterLogForwarder` exists for container logs.
- **ACM Integration:** Utilize ACM (Advanced Cluster Management) to streamline deployment and enforce consistency.
- **Monitoring & Verification:** Track relevant events and validate deployment correctness.
- **Drift Management:** Implement strategies to detect and correct configuration drift.
- **Policy Validation:** Define and enforce policies to ensure pipeline and infrastructure consistency.

## Workshop Walkthrough
### 1. Deploy Bookinfo Application
- Deploy the **Bookinfo** application into your development cluster using the CLI within your assigned project.

### 2. Deploy Pipeline via ArgoCD
- Deploy a pipeline using **ArgoCD** into the dev cluster.
- The ArgoCD project will have a naming convention following: `your-project-name-gitops` (e.g., `anaeem-gitops`).

### 3. Policy Creation
- **Namespace Policy:** Ensure that the expected namespace exists.
- **Pipeline Policy:** Validate that the required pipeline is deployed and functional.
- **Operator Policy:** Check that the necessary operators are installed and running.

## Prerequisites
Before starting, ensure you have:
- Access to a **development Openshift cluster**.
- Installed **oc**, **tkn**, **git** 

## Summary
This workshop provides practical insights into deploying microservices, monitoring workloads, and managing infrastructure consistency using ACM and ArgoCD. By following these steps, you will gain hands-on experience with real-world deployment and policy enforcement techniques.

Happy coding! 🚀


