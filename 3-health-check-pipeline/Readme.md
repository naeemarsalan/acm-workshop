# **OpenShift Pipeline: Check Pods Readiness**

This project provides a **Helm chart** to deploy a **Tekton pipeline** that monitors the health of all pods in an OpenShift project. The pipeline ensures that all bookinfo pods reach a **Ready** state before proceeding.

---

## **Why Use a Helm Chart?**

Using Helm allows for easy deployment and configuration management. Since the **project name** needs to be dynamically overridden per environment, Helm enables this by allowing values to be customized at install time.

### **Benefits of Helm:**
- **Parameter Overrides** – Easily configure values like project names without modifying YAML files.
- **Simplified Deployment** – One command deploys all Tekton resources.
- **Version Control** – Helm makes upgrades, rollbacks, and versioning easier.
- **Reusable & Scalable** – The same chart can be used across different environments.

---

## **Tekton Resources Explained**

The Helm chart deploys the following Tekton resources:

### **1️⃣ Pipeline**
- Defines the process to check if pods in a project are ready.
- Uses a parameterized **project name** so it can work in multiple environments.

### **2️⃣ PipelineRun (Triggered via EventListener & CronJob)**
- Instantiates a new run of the pipeline when triggered.
- Uses the **project name** override set via Helm values.

### **3️⃣ TriggerTemplate**
- Defines how the pipeline is triggered dynamically.
- Generates a `PipelineRun` with the correct project name.

### **4️⃣ TriggerBinding**
- Binds the incoming request (e.g., from a cron job) to the pipeline parameters.
- Ensures the correct project name is passed when the pipeline runs.

### **5️⃣ EventListener**
- Exposes an HTTP endpoint that listens for incoming requests to start the pipeline.
- Can be triggered by a **CronJob** or external event.

### **6️⃣ OpenShift CronJob**
- Automates the pipeline execution at scheduled intervals.
- Calls the **EventListener** to start a pipeline run at the defined schedule (e.g., every 5 minutes).

---

## **Installation**

To deploy the pipeline using Helm:

```sh
helm install check-pods-pipeline ./health-check -n <your-namespace> \
  --set projectName=<your-project> \
  --set schedule="0/5 * * * *" 
```

To update an existing deployment:

```sh
helm upgrade check-pods-pipeline ./health-check -n <your-namespace> \
  --set projectName=<your-project> \
  --set schedule="0/5 * * * *" 
```

To uninstall:

```sh
helm uninstall check-pods-pipeline -n <your-namespace>
```

---

## **Summary**
✔ Deploys a Tekton pipeline to monitor pod readiness.
✔ Uses Helm to simplify deployment and configuration.
✔ Automates execution with an EventListener and a CronJob.
✔ Enables easy project name overrides for multi-environment support.

This Helm chart ensures your OpenShift pods are **ready** before further actions, providing a reliable automation workflow. 🚀



By the end of this workshop, you will have accomplished the following:

Pipeline Deployment: Set up a pipeline to monitor workload health.
Deploy Bookinfo App: Deploy a real-world microservices application.
Create Monitoring Pipelines:
Ensure the health of the Bookinfo application.
Verify that ClusterLogForwarder exists for container logs.
ACM Integration: Utilize ACM (Advanced Cluster Management) to streamline deployment and enforce consistency.
Monitoring & Verification: Track relevant events and validate deployment correctness.
Drift Management: Implement strategies to detect and correct configuration drift.
Policy Validation: Define and enforce policies to ensure pipeline and infrastructure consistency.