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

To deploy the Simple Node.js application on your Amazon EKS cluster, follow these steps given in Deployment file.

Deployment Output:
Upon successful deployment, you can expect the following information:

Service Information:
* Run the following command to retrieve details about the deployed service:
- kubectl get service
(Look for the external IP/DNS under the "EXTERNAL-IP" column.)

*Accessing the Application:
- Use the obtained external IP/Loadbalance DNS to access the Node.js application.

![Screenshot 2024-01-18 191104](https://github.com/RajputRenu/EKS_Project/assets/118665146/bb4ed26d-428f-4782-8c7a-087778085af5)


- Open a web browser and navigate to http://EXTERNAL-IP, replacing EXTERNAL-IP with the actual IP/DNS.

*Once you Browser and Navigate to LoadBalancer DNS> External_IP. You will see the OutPut as Shown in Image.

![Screenshot (149)](https://github.com/RajputRenu/EKS_Project/assets/118665146/2118cf52-c062-4eaf-87c7-c47e843b49eb)

Congratulations on successfully deploying the Node.js application! 
