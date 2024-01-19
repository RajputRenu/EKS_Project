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


Deploying the Node.js Application:

To deploy the Node.js application on your Amazon EKS cluster, follow these steps given in Deployment file.

Deployment Output:
Upon successful deployment, you can expect the following information:

Service Information:
* Run the following command to retrieve details about the deployed service:
- kubectl get service
(Look for the external IP/DNS under the "EXTERNAL-IP" column.)

*Accessing the Application:
- Use the obtained external IP/Loadbalance DNS to access the Node.js application.


- Open a web browser and navigate to http://EXTERNAL-IP, replacing EXTERNAL-IP with the actual IP/DNS.
  
