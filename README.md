# Nodejs Application Deployment on EKS with HA using Helm and NLB
This project demonstrates the deployment of a Node.js application on Amazon EKS using Helm, a powerful package manager for Kubernetes.Helm simplifies the process of deploying and managing applications by packaging them into customizable charts.

Prerequisites:
AWS Account
AWS CLI installed and configured
Terraform installed
kubectl installed
Helm installed
EKS Cluster Configuration
Nodejs Application Code


1. Set Up Your EKS Cluster
   Make sure you have an EKS cluster set up on AWS. You can use the AWS Management Console or AWS CLI to create your cluster.
2. Install kubectl and helm
   Make sure you have kubectl and helm installed on your local machine.
# Install kubectl
kubectl version --client

# Install Helm
# On Linux or macOS
 curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
 
 chmod 700 get_helm.sh
 
  ./get_helm.sh

3. Create a Node.js Application
4. Create a simple Node.js application.for example, you can create a file named app.js 


     
