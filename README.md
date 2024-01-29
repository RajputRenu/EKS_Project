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

Step 1
--------
First Install Terraform on AWS Instance:

1] Add Terrafrom APT Repository:-
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/f4c5f314-e43c-4499-882d-afc1c09507b5)

2] Install Terraform using Apt Command:-
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/16d2f970-32f5-4a9a-8972-e18eeed73b01)

3]Post terraform installation, verify its version:-
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/f9d50d05-1bed-49aa-88e9-367657cf1cbd)

Step 2
-------
Clone The Repository :-
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/f27ada7c-961b-43f8-a1a1-e40d5fd25891)

Follow the Commands as shown:- 
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/4868aa60-f667-4d1c-a4af-c230d3cbffa6)

Configure AWS in Instance:-
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/43a28d0a-2854-40c0-93f2-f5dd57d2373b)

Terraform Commands:- 

1] terraform init:- 
The terraform init command is used to initialize a Terraform working directory. 
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/069f9293-2a93-4193-a630-e679869393c3)

2] terraform validate:-
The terraform validate command is used to check the syntax and validity of the Terraform files in the working directory.
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/dc1a5da9-fcf4-49b0-9727-ad136c0a26f9)

3] terraform plan:-
The terraform plan command is used to create an execution plan, which is a detailed preview of what changes Terraform will make to your infrastructure.
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/7d3c9dea-83e4-4c08-abfe-b71c73fb926c)

4] terraform apply:-
The terraform apply command is used to apply the changes proposed in the execution plan created by terraform plan.
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/b3978428-078f-488d-9105-9794d09e3ec6)

![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/9ed58b44-6a75-4cdf-b86a-8aa0d42d90c3)

AWS Comsole :- 
1] EC2 Instance:-
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/cd2ecdd4-ae8a-4365-a418-d5b79b12bdd3)

2] VPC :-
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/92053ac2-987d-4703-9861-4ddcb2455de8)
Subnet:- 
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/d4cd2f11-058f-43bc-aea6-dc8207bf834f)

3] EKS :-
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/11e6509c-26a9-4649-91b1-a7043a92b116)


Now Install Kubectl & Helm on AWS EKS
# Install kubectl
Follow this link to Install Kubectl
https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html

Commands to Follow:-
1] Download the kubectl binary for your cluster's Kubernetes version from Amazon S3.
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/c7234e51-0c1f-44e1-bd12-00c2be6331be)

2] Download the SHA-256 checksum for your cluster's Kubernetes version from Amazon S3 using the command for your device's hardware platform. The first link for each version is for amd64 and the second link is for arm64.
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/595f0766-10ba-42fe-a90e-e21fae307d58)

3] Check the SHA-256 checksum for your downloaded binary with one of the following commands.
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/3714d1d4-0f21-41bf-a598-ad6fe44fbc0a)

4] Apply execute permissions to the binary.
[ chmod +x ./kubectl ]
[mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$HOME/bin:$PATH]
[kubectl version --client]

5] Configure AWS to Instance which was created :-
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/2d87f738-de5c-408a-a33c-e552b698307e)

# Install Helm
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/995bf1e6-c04c-4667-b245-2c3d77714554)


Step 3
------
Create a Node.js Application
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/b1ae9296-9640-43a6-9aaf-6e54392fe099)

Step 4
--------
Create a Helm Chart
1] 
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/7436b09c-2ea3-4c84-b537-682a6eec8a2b)

 
Step 5
---------
Update values.yaml:
Modify the values.yaml file in your Helm chart to include the service type and annotations for NLB
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/f3f7754f-9c60-4c1a-98d4-a0bb64b43e56)


Step 6
----------
Update templates/service.yaml:
Modify the templates/service.yaml file to set the service type and add NLB annotations
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/5a89da61-d602-4ac9-8187-7d0a3e0c86e5)


Step 7
----------
Package and Deploy the Updated Helm Chart: (example)
- helm package my-nodejs-apps
![image](https://github.com/RajputRenu/EKS_Project/assets/118665146/76d8eb22-c30f-4a83-af0c-4e6525b2814f)


Deploy the updated Helm chart to your EKS cluster: (example)
- helm upgrade --install my-nodejs-app-release ./my-nodejs-app-0.1.0.tgz

Step 8
----------
Service Information:
* Run the following command to retrieve details about the deployed service:
- kubectl get service
(Look for the external IP/DNS under the "EXTERNAL-IP" column.)

Step 9
------------
*Accessing the Application:
- Use the obtained external IP/Loadbalance DNS to access the Node.js application.

![Screenshot 2024-01-18 191104](https://github.com/RajputRenu/EKS_Project/assets/118665146/bb4ed26d-428f-4782-8c7a-087778085af5)


*Once you Browser and Navigate to LoadBalancer DNS> External_IP. You will see the OutPut as Shown in Image.

![Screenshot (149)](https://github.com/RajputRenu/EKS_Project/assets/118665146/2118cf52-c062-4eaf-87c7-c47e843b49eb)

Congratulations on successfully deploying the Node.js application! 
