# Nodejs Application Deployment on EKS with HA using Helm and NLB

This project demonstrates the deployment of a Node.js application on Amazon EKS using Helm, a powerful package manager for Kubernetes.Helm simplifies the process of deploying and managing applications by packaging them into customizable charts.

Prerequisites:
1. AWS Account
2. AWS CLI installed and configured
3. Terraform installed
4. kubectl installed
5. Helm installed
6. EKS Cluster Configuration
7. Nodejs Application Code 

Steps For Deploying the Nodejs application on AWS EKS using Terraform

Step 1
--------
First Install Terraform on AWS Instance

Step 2
-------
Now Install Kubectl & Helm on AWS EKS
# Install kubectl
Follow this link to Install Kubectl
https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html
kubectl version --client

# Install Helm
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash

Step 3
------
Create a Node.js Application

Step 4
--------
Create a Helm Chart

Step 5
---------
# Update values.yaml:
Modify the values.yaml file in your Helm chart to include the service type and annotations for NLB

Step 6
----------
# Update templates/service.yaml:
Modify the templates/service.yaml file to set the service type and add NLB annotations

Step 7
----------
# Package and Deploy the Updated Helm Chart: (example)
- helm package my-nodejs-apps 

# Deploy the updated Helm chart to your EKS cluster: (example)
- helm upgrade --install my-nodejs-app-release ./my-nodejs-app-0.1.0.tgz

Step 8
----------
# Check the status of your service:
- kubectl get services

Step 9
------------
- Copy the DNS of Loadbalancer/ IP address of instance and paste it in browser.


![Screenshot 2024-01-18 191104](https://github.com/RajputRenu/EKS_Project/assets/118665146/0ff192e8-6994-4952-966f-ae3c5d9bf6f3)

Conclusion - Final Output:
Congratulations! 🚀 You have successfully deployed the Node.js application on your Amazon EKS cluster using Helm.
The final output:- 

![Screenshot (149)](https://github.com/RajputRenu/EKS_Project/assets/118665146/8d4a84cf-ad0e-4fc8-9914-1bdb70a72abd)
