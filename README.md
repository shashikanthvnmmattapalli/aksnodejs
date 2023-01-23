## Overview
This sample shows how to run a Nodejs and mongodb app on Azure Kubernetes Services and create a Jenkins Server using Windows PowerShell.

## Please follow below steps to deploy the code into aks

Step 1 : To up the Jenkins Server and install the docker  in Azure linux machine run the script vmcreation.ps1 

i) Before running the script define Application ID, ClientSecret, TenantID, SubscriptionID it will authenticate azure portal

ii) After that it will prompt to enter the resourcegroup, storage account, Azure Container registry and vm details , Please define accrodingly. 

iii) Note : Once the Jenkins Sever is installed in the vm you can get the admin password from the path 'C:\Users\admin\Desktop\jenkins.txt', you can change according to your workspace.


Step 2 : Once the Step 1 finishes , login into the Jenkins and install all the pre defined plugins .

Step 3 :  Run the script installpluginsjenkinscript.sh, this script installs all the required plugins .

Step 4 : Once the installation is completed restart the Jenkins Server.

Step 5 : Now run the script uploadcredentials into Jenkins Manage Credentials , this credentials upload storage account key, Azure container registry credentials , Azure service principal, Kubernetes cluster name, resource group name.

Step 6 : Now run the script jobscript.sh to create a job in Jenkins Server and run the job or copy the Jenkinsfile and create a Project in Jenkins, paste the file and run it .






