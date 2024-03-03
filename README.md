# AWS CLI
The AWS Command Line Interface (AWS CLI) is a command line tool that provides an interface for interacting with products and services from Amazon Web Services (AWS).
We can install the AWS CLI on our local machine or a virtual machine such as an Amazon Elastic Compute Cloud (Amazon EC2) instance.

I installed and configured the AWS CLI on a Red Hat Linux instance because this instance type does not have the AWS CLI pre-installed. Some instance types, such as Amazon Linux, do come pre-installed with the AWS CLI. 
During this project, I established a Secure Shell (SSH) connection to the instance. I configured the installation with an access key that can connect to an AWS account. Finally, I have accomplished the AWS CLI to interact with AWS Identity and Access Management (IAM).


# Objectives
After completing this project, I am able to do the following:
- Install and configure the AWS CLI.
* Connect the AWS CLI to an AWS account.
+ Access IAM by using the AWS CLI.

After finishing the project, the architecture will reflect as follows:
![archi_diagram (1)](https://github.com/merinsk/aws_CLI/assets/159441724/b00f136f-94ca-4a8c-aa12-2f92e3c2c4ee)

## Step 1: Connect to the Red Hat EC2 instance by using SSH
These following steps are specifically for Mac and Linux users:
- At the top of the AWS Management Console page, choose the  _Details_ dropdown menu, and then choose _Show_. A Credentials window opens.
- Choose Download PEM, and save the labsuser.pem file.
- Copy and paste the PublicIP into a text editor to use later. This IP address is the IPv4 server address that you have to connect to.
- To exit the Details panel, choose the X.
- Open a terminal window, and change the cd directory to the directory where you downloaded the labsuser.pem file. For example, run the following commands:
* cd ~/Downloads
* chmod 400 labsuser.pem
* ssh -i labsuser.pem ec2-user@<ip-address> (replace <ip-address> with the public IP address that you copied from the previous steps)

## Step 2:
