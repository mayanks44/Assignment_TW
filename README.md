# Assignment_TW

# This Repository is a collection of Implementation documents.




# Purpose:
# By following this repository you can able to setup a DevOps CI/CD Pipeline using
Jenkins
Ansible
Docker 
Kubernetes &
Helm




# Below are the steps for infra set up, instalation guide and deploying mediawiki application on kubernetes cluster

1- Jenkins:
    - Go to Jenkins folder 
    - Follow Jenkins Installation MD file
    - Open jenkins server ip with 8080 port in browser
    - Check Jenkins should be up and running. 

2- Ansible:
    - Go to Ansible folder 
    - Follow Anisble and Docker Installation MD file
    - Follow Jenkins_Ansible Integration file.
    
3- Kubernetes:
    - Go to kubernetes folder 
    - Follow Kubernetes Cluster formation file
    - Follow Anisble_KubernetesCluster Integration file.

4- Helm:
    - Go to Helm folder 
    - Follow Helm Chart formation file.
    
5- Once all above set up is completed then go to Jenkins UI 
    - Run k8 Demo CI job
    - Check for CI job status
    - Check for downstreaming CD job
    - Check for CD job status.
6- Once both CI and CD jobs are success then open host(node where container is up) ip with port 80. 

7- Mediawiki webapp is up and running. 
