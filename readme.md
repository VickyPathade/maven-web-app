Set up AWS Account
Create ec2 instance
Create IAM role and attached to the instance with neccessery permission
Add below permissions for the role

IAM - fullaccess 
VPC - fullaccess 
EC2 - fullaccess 
CloudFomration - fullaccess 
Administrator - acces 
Enter Role Name

connect the ec2 instance using any SSH like putty
install git 
sudo apt install git

Install Docker in Amazon ubuntu

sudo apt update -y
sudo apt install docker.io -y
sudo systemctl start docker
sudo usermod -aG docker ubuntu


 Create EKS Management Host in AWS Launch new Ubuntu VM

 install kubectl using below commands
 
 $ curl -o kubectl https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/linux/amd64/kubectl $ chmod +x ./kubectl $ sudo mv ./kubectl /usr/local/bin $ kubectl version --short --client

 Install AWS CLI latest version using below commands

$ sudo apt install unzip $ cd $ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" $ unzip awscliv2.zip $ sudo ./aws/install $ aws --version

Install eksctl using below commands

$ curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp $ sudo mv /tmp/eksctl /usr/local/bin $ eksctl version

 Create EKS Cluster using eksctl Syntax:

eksctl create cluster --name cluster-name --region region-name --node-type instance-type --nodes-min 2 --nodes-max 2 \ --zones ,

N. Virgina: $ eksctl create cluster --name your-cluster-name-cluster4 --region your-region --node-type t2.medium --zones us-east-1a,us-east-1b

Note: Cluster creation will take 5 to 10 mins of time (we have to wait). After cluster created we can check nodes using below command.

$ kubectl get nodes

Note: We should be able to see EKS cluster nodes here.


Jenkins Installation:

Install Java In Ubuntu VM with below commands
$ sudo apt-get update
$ sudo apt-get install default-jre

Install Jenkins in Ubuntu VM with below commands

$ curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

$ echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

$ sudo apt-get update

$ sudo apt-get install jenkins

$ sudo systemctl status jenkins
 
 Access Jenkins Server in browser using below URL

		URL : http://ec2-public-ip:8080/

	Note: Enable 8080 port in security group
 
 Get the initial administrative password 

	$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword

	pwd : 5fe6ddcc9db244cab6aca5ccf2d6a83a

-> Provide pwd which we have copied to unlock jenkins

-> Select "Install Suggested Plugins" card (it will install those plugins)
