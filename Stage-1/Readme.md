---

# **Deploying Bookinfo to Your OpenShift Project**

In this step, you will create your own project and deploy the **Bookinfo** application on the downstream cluster named **"dev"**. Ensure you are logged into the cluster before proceeding.

## **Steps to Follow**

1. **Create a New OpenShift Project**  
   Run the following command to create your own project:  
   ```sh
   oc new-project <your-project-name>
   ```

   **Optional: Switch to Your Project**  
   Use this command to change to a project:  
   ```sh
   oc project <your-project-name>
   ```

2. **Deploy the Bookinfo Application**  
   Apply the `bookinfo.yaml` manifest to deploy the application:  
   ```sh
   oc apply -f bookinfo.yaml
   ```

3. **Wait for All Pods to be Ready**  
   Run the following command to monitor the deployment and wait until all pods are ready:  
   ```sh
   oc wait --for=condition=Ready pods --all --timeout=300s
   ```

4. **Expose the Productpage Service**  
   To make the **productpage** service accessible externally, expose it using a route:  
   ```sh
   oc expose svc productpage
   ```

5. **Retrieve the Route URL**  
   Get the URL of the exposed service to access the application:  
   ```sh
   oc get route productpage -o jsonpath='{.spec.host}'
   ```

Once these steps are complete, your Bookinfo application should be up and running in your project on the **"dev"** cluster. 🚀

---

