# MLOps
**Group 1 Assignment 1**<br>
if you can see this file you are in correct mlops01 repo.<br><br>
Please fork your own branch.
# 1. For Gcloud
echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list
sudo apt-get update && sudo apt-get install google-cloud-cli
## inside Docker:
RUN echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | tee -a /etc/apt/sources.list.d/google-cloud-sdk.list && curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo gpg --dearmor -o /usr/share/keyrings/cloud.google.gpg && apt-get update -y && apt-get install google-cloud-cli -y
gcloud init<br>
# 2. Deploy the Model Using Kubernetes
## Step 1: Create a Docker Image of Your Model
## Step 2: Write Kubernetes Deployment and Service YAML
## Step 3: Apply the YAML Files
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
## Step 4: Verify the Deployment
kubectl get pods
kubectl get services

# 3. Create a Helm Chart
helm version
helm create model-chart
<br>
## Step 3: Modify Chart Files
helm package model-chart
helm install <release-name> ./model-chart

helm list
kubectl get pods
kubectl get services

helm uninstall <release-name>
kubectl delete -f deployment.yaml
kubectl delete -f service.yaml


