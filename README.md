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

## Connect to the Red Hat EC2 instance by using SSH
These following steps are specifically for Mac and Linux users:
- At the top of the AWS Management Console page, choose the  _Details_ dropdown menu, and then choose _Show_. A Credentials window opens.
- Choose Download PEM, and save the labsuser.pem file.
- Copy and paste the PublicIP into a text editor to use later. This IP address is the IPv4 server address that you have to connect to.
- To exit the Details panel, choose the X.
- Open a terminal window, and change the cd directory to the directory where you downloaded the labsuser.pem file. For example, run the following commands:
* cd ~/Downloads
* chmod 400 labsuser.pem
* ssh -i labsuser.pem ec2-user@<ip-address> (replace <ip-address> with the public IP address that you copied from the previous steps)

## Install the AWS CLI on a Red Hat Linux instance
To install the AWS CLI on a Red Hat Linux instance, do the following steps from the terminal window:
- curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" (To write the downloaded file to the current directory)
- unzip -u awscliv2.zip (To unzip the installer)
- sudo ./aws/install (To run the install program)
- aws --version (To confirm the installation)
- aws help (The help command displays the information for the AWS CLI)

## Observe IAM configuration details in the AWS Management Console
To observe the IAM configuration details for the EC2 instance in the AWS Management Console, do the following steps:
- In the AWS Management Console, in the Search box, enter _IAM_ and choose IAM. This option takes you to the IAM console page.
- In the navigation pane, choose Users, and then choose awsstudent.
- You are now in the _Permissions_ tab. Next to lab_policy, choose the arrow icon, and then choose the {} _JSON_ button.
- This lab_policy document is formatted in JSON. The IAM policy grants the awsstudent user access to specific AWS services in this account.
- Choose the _Security credentials_ tab. In the Access keys section, locate the awsstudent user's _access key ID_. 

## Configure the AWS CLI to connect to your AWS Account
- In the SSH session terminal window, run the configure command for the AWS CLI:
  aws configure
- At the prompt, configure the following:
  AWS Access Key ID: Choose the Details dropdown list, and choose Show. Copy and paste the AccessKey value into the terminal window.
  AWS Secret Access Key: Copy and paste the SecretKey value into the terminal window.
  Default region name: Enter us-west-2
  Default output format: Enter json

## Observe IAM configuration details by using the AWS CLI
Here, you observe the IAM configuration details for the EC2 instance using the AWS CLI by running the following command in the terminal window:
- aws iam list-users (A successful test shows a JSON response that includes a list of IAM users in the account)

## Download the lab_policy document in a JSON-formatted IAM policy document
Use the AWS CLI Command Reference documentation and AWS CLI to download the lab_policy document in a JSON-formatted IAM policy document. This is the same document that is in the AWS Management Console. 










