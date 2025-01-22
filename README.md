Entire workflow for deployment of static website on AWS Kubernetes cluster using Terraform and Prometheus for monitoring.

Steps:

Terraform Configuration - (using help from Terraform documentation)
Setup provider, region, vpc in atleast 2 AZ, security group, IAM permissions. Also, provide cluster name for k8s
Run terraform init, terraform plan, and terraform apply to create resources
----------------------------
Dockerfile for containerization

Install nginx and create folder htpods and copy index.html there
Change root of config file to location on index.html

Build the Docker image by running f/w command:
 docker build -t web-app .

Push the image to a container registry: 
docker push pass3101/web-app:latest 
#pass3101 is my registry
----------------------------
Create k8s deployment files (deployment, namespace, service) - (using help from K8s documentation)
Define Kubernetes manifests for deploying the web application.

Namespace: Create a namespace to organize resources.
Deployment: Define a deployment with replicas for the application.
Service: Create a service to expose the application.

Commands:
Apply namespace: kubectl apply -f namespace.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
----------------------------

Create monitoring solution using Prometheus
Set up a monitoring solution to collect metrics from the Kubernetes cluster and web application using Helm.

Command:
helm install prometheus prometheus-community/kube-prometheus-stack
----------------------------

Run app using external IP and verify
----------------------------
----------------------------
