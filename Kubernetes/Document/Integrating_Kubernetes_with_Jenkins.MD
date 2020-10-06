## Integration Kubernetes with Jenkins

# *Jenkins CI Job:* `Deploy_on_Kubernetes-CI`

### Pre-requisites

1. Jenkins server 
1. Ansible server
1. Kubernetes cluster
 
### Steps to create "Deploy_on_Kubernetes_CI" Jenkin job
#### From Jenkins home page select "New Item"
   - Enter an item name: `Deploy_on_Kubernetes_CI`
    
 - *Pre-Steps*
   - Send build artifacts over SSH
     - *SSH Publishers*
      - SSH Server Name: `ansible-server`
       - `Transfers` >  `Transfer set`
           - Source files: `webapp/target/*.war`
	       - Remove prefix: `webapp/target`
	       - Remote directory: `//opt//docker`
	       - Exec command: 
                ```sh 
                ansible-playbook -i /opt/docker/hosts /opt/docker/*****-image.yml;
                ```
  
  - *Post-Build-Action*
    - Build with other projects
      - Project to Builds: Select CD job from list
        - Trigger Only if build is stable
  
Save and run the job.

# *Jenkins CD Job:* `Deploy_on_Kubernetes-CD`

### Steps to create "Deploy_on_Kubernetes_CI" Jenkin job
#### From Jenkins home page select "New Item"
   - Enter an item name: `Deploy_on_Kubernetes_CI`
     - Freestyle Project
	 
  - *Post-build Actions*  
    - Send build artifacts over SSH  
      - *SSH Publishers*  
	       - Exec command: 
                ```sh 
                ansible-playbook -i /opt/docker/hosts /opt/docker/******-deployment.yml;
                ansible-playbook -i /opt/docker/hosts /opt/docker/******-service.yml;
                ```
Save and run the job.
