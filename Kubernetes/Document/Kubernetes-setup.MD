# Setup Kubernetes (K8s) Cluster on AWS


1. Create Ubuntu EC2 instance
2. install AWSCLI
   ```sh
    curl https://s3.amazonaws.com/aws-cli/awscli-bundle.zip -o awscli-bundle.zip
    apt install unzip python
    unzip awscli-bundle.zip
    ./awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws
    ```

3. Install kubectl on ubuntu instance
   ```sh
   curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
    chmod +x ./kubectl
    sudo mv ./kubectl /usr/local/bin/kubectl
   ```

4. Install kops on ubuntu instance
   ```sh
    curl -LO https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64
    chmod +x kops-linux-amd64
    sudo mv kops-linux-amd64 /usr/local/bin/kops
    ```
4. Create an IAM user/role  with Route53, EC2, IAM and S3 full access

5. Attach IAM role to ubuntu instance
   ```sh
   # Note: If you create IAM user with programmatic access then provide Access keys. Otherwise region information is enough
   aws configure
    ```

5. Create a Route53 private hosted zone (you can create Public hosted zone if you have a domain)
   ```sh
   Routeh53 --> hosted zones --> created hosted zone  
   Domain Name: ******
   Type: Private hosted zone for Amzon VPC
   ```

6. create an S3 bucket
   ```sh
    aws s3 mb s3://*****
   ```
7. Expose environment variable:
   ```sh
    export KOPS_STATE_STORE=s3://*****
   ```

8. Create sshkeys before creating cluster
   ```sh
    ssh-keygen
   ```

9. Create kubernetes cluster definitions on S3 bucket
   ```sh
   kops create cluster --cloud=aws --zones=ap-southeast-1a --name=****** --dns-zone=****** --dns private 
    ```

10. Create kubernetes cluser
    ```sh
    kops update cluster ****** --yes
    ```

11. Validate your cluster
     ```sh
      kops validate cluster
    ```

12. To list nodes
   ```sh
   kubectl get nodes
   ```

13. To connect to K8 cluster master node-
   ```sh
   ssh -i ~/.ssh/id_rsa username@api.******
   ```

