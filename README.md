# aws_cli_mfa_helper
AWS CLI Multi-Factor-Authentication Helper

## Pre-requisites:

### 1) Install required dependencies

$ sudo yum install python jq  
$ curl "https://s3.amazonaws.com/aws-cli/awscli-bundle.zip" -o "awscli-bundle.zip"  
$ unzip awscli-bundle.zip  
$ ./awscli-bundle/install -b ~/bin/aws  
$ export PATH=~/bin:$PATH  
$ vi ~/.aws/credentials  

### 2) Create ~/.aws/credentials

[default]  
output = json  
region = eu-west-1  
mfa_serial = [User ARN]  
aws_access_key_id = [User Access Key ID]  
aws_secret_access_key = [User Secret Access Key]  

## Run

This script should be called on a bash shell or inside a bash script. It will set all requried variables for the AWS CLI to work.

$ source ./awscli_mfa_init.sh [MFA Token]
