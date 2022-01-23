# Kind-Pods-Cluster
Some people are experiencing challenges whenever they are trying to connect with the Google Kubernetes Cluster using Jenkins in the process of deploying
the image application to the live production environment. 

Jenkins is not connecting with the Google Kubernetes Cluster because of the following issues: 

You have not created a service account that you will use to create a role binding to give Jenkins the ability to connect with the cluster.

To create a service account, you will need first to create a namespace called jenkins. 

To do so, run the command # kubectl create namespace jenkins  

After creating the namespace, create a service account that will target the namespace you created 

After creating the service account, the Google Kubernetes cluster is going to generate a token that you will need to add to jenkins to resolve the issue of synonymous account

Creating the service account and obtaining the token certificate connected to the account is not enough

You must create a role binding to permit the service account to access the cluster kind pods. 

Test the connection, and the cluster will request you to provide a kubeconfig certificate. 

Go to cluster and run the command # cd .kube 

This will allow you to be in the .kube directory 

Run the #ls 


You should see a file called CONFIG 

Cat the config file content by running the command # cat config 

Copy the certificate, go to visual studio code, create a file and paste the config information. 

Save the file on the desktop or your favorite file explorer location

Go to jenkins, create a secret file and upload it. 

Test connection, and everything should work perfectly. 
