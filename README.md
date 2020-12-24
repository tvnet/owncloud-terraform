# owncloud-terraform
**Owncloud-terraform-aws** - Finish project, for testing purporse.
Owner - Marina M.

**Installation OwnCloud on AWS via terraform.**
 
 
 <h2> Pre-requisites: </h2>
 
* Terraform has to be installed.
* AWS account (free), AWS keys
* Login in aws cli by command via terminal
 aws configure
* Linux Ubuntu 16

<h2> Action </h2>
  1. Create a folder mkdir for terraform project
mkdir terrformowncloud

  1. Copy their main.tf, vars.tf and provision.sh

  1. Fill in variables in vars.tf

1. In terraform project folder, use Linux terminal and write command and press Enter:
 * terraform init
 
Waiting plugin aws will be downloaded.

* terraform plan 

If there is no issues, use the next command

* terraform apply


1. When terraform is installed, login to your AWS account and check if you have been added with a proper security group, if no, manualy put checks for Owncloud security group

1. Via Linux console login via ssh *.pem file to your created environment and check docker version

 * docker -version

If docker was not installed, the provision.sh script should be copied to created environment.

Doing it by command, change location pem file /path/to/ssh, and username and dnspublicname.

 * scp  ./provision.sh -i /path/to/ssh username@dnspublicname:/tmp/provision.sh
 
1. Login to aws instance via ssh
 
 * ssh -i /path/to/ssh username@dnspublicname
 
1.  Script should run on AWS, so go to folder tmp:

* cd /tmp/

* and run script ./provision.sh and run with arguments !!! 
* and check vim provision.sh - there can be default meaning.
 
 Change on your variables. 

1. Go to folder 
cd ~ 

Run sudo docker-compose up -d  (in the same folder, where is docker-compose.yml).

10. Check docker ps -a (if all necessary docker images are running)


11. From your local (dnspublic should be manually changed) mashine use http://dnspublic/80 or http://dnspublic/8080

12. If you don't use and don't need, from local machine destroy instance:
      terraform destroy
