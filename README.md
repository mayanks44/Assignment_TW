# Assignment_TW

# This Repository is a collection of Implementation documents.




# Purpose:
# By following this repository you can able to setup a DevOps CI/CD Pipeline using

Jenkins,
Ansible,
Docker,
Kubernetes &
Helm




# Below are the steps for infra set up, instalation guide and deploying mediawiki application on kubernetes cluster

1- Jenkins:
    -> Go to Jenkins directory 

    -> Follow Jenkins Installation MD file
    
    -> Follow Git Installation MD file

    -> Open jenkins server ip with 8080 port in browser

    -> Check Jenkins should be up and running. 

2- Ansible:
    -> Go to Ansible directory 

    -> Follow Anisble and Docker Installation MD file

    -> Follow Jenkins_Ansible Integration file.
    
    -> Connect to Ansible server and Create directory mkdir /opt/demo-k8s
    
    -> Move all files from the https://github.com/mayanks44/Assignment_TW/tree/master/Ansible/demo-k8s directory to an/opt/demo-k8s directory
     
3- Kubernetes:
    -> Go to kubernetes directory  

    -> Follow Kubernetes-setup.MD file
    
    -> Follow Integrating_Kubernetes_with_Ansible.MD

    -> Follow Integrating_Kubernetes_with_Jenkins.MD file.
    
    -> Connect to Kubernetes Master server and Create directory mkdir /home/username/k8-demo1 
    
    -> Move all files and folders from https://github.com/mayanks44/Assignment_TW/tree/master/Kubernetes/k8-demo1 directory to /home/username/k8-demo1 

4- Helm:
    -> Go to Helm directory 

    -> Follow Helm Chart formation file.
    
5- Once all above set up is completed then go to Jenkins UI 
    -> Run k8 Demo CI job

    -> Check for CI job status

    -> Check for downstreaming CD job

    -> Check for CD job status.

6- Once both CI and CD jobs are success then open host(node where container is up) ip with port 80. 

7- Mediawiki webapp is up and running. 
