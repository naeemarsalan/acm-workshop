# **OpenShift Pipeline: Check Pods Readiness**  

This guide walks you through setting up a **Tekton pipeline** to monitor the health of all pods in an OpenShift project. The pipeline ensures that all pods are in a **Ready** state before proceeding.  

---

## **Prerequisites**  
Before running the pipeline, ensure you have:  
✅ Access to an OpenShift cluster  
✅ The OpenShift CLI (`oc`) installed  
✅ Tekton (`tkn`) installed and configured  
✅ Your own project selected

---

## **Step 1: Create a Service Account**  

The pipeline requires a **ServiceAccount** with sufficient permissions to check pod status. Create and assign the required permissions:  

### **1.1 Create the Service Account**
```sh
oc create sa pipeline-sa 
```

### **1.2 Assign Permissions**
```sh
oc adm policy add-role-to-user edit -z pipeline-sa 
---
```

## **Step 2: Deploy the Tekton Pipeline**  

### **2.1 Apply the Pipeline Definition**  
Apply the pipeline:
```sh
oc apply -f check-pods-pipeline.yaml 
```

---

## **Step 3: Run the Pipeline**  

Start the pipeline with:  
```sh
tkn pipeline start check-pods-ready \
  -p project-name=<your-project> \
  --serviceaccount pipeline-sa \
  -n <your-namespace>
```

Monitor execution:  
```sh
tkn pipelinerun logs -f -n <your-namespace>
```

---

## **Step 4: Verify Results**  
If all pods are **ready**, the pipeline will complete successfully. Otherwise, it will time out or fail, indicating issues with the pods.

---

### **🎯 Summary**  
✔ Created a **ServiceAccount** with the required permissions  
✔ Defined a **Tekton pipeline** to check for pod readiness  
✔ Deployed and executed the **pipeline**  

Now, your OpenShift pipeline can automatically ensure all pods are running before further deployment steps! 🚀  

