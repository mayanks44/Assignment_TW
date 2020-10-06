# Integrating Kubernetes cluster with Ansible

1. Login to ansible server and copy public key onto kubernetes cluseter master account 
Ansible Server- 
cd /home/user/.ssh
vim id_rsa.pub
copy key

Kubernetes Master Account-
cd /home/user/.ssh 
vim authorized_keys
Paste Copied Public key from Ansible server and Save it

2. Update hosts file in ansible server with new group called kubernetes and add kubernetes master ip in that. 

3. Create ansible playbooks to depoy Helm Chart or Kubernetes Deployment and Service 
