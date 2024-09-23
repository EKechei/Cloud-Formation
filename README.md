# Project Title:Basic Architecture with a VPC, Subnets, and an EC2 Instance

## Description
This project sets up a scalable cloud infrastructure on AWS using a CloudFormation template. It provisions a Virtual Private Cloud (VPC) with public and private subnets, an Internet Gateway, and an EC2 instance for hosting applications.

## CloudFormation Template Overview
The CloudFormation template (`Cloudforce-Challenge.yml`) defines the following resources:

- **VPC**: Creates a Virtual Private Cloud with a CIDR block of `10.0.0.0/16`, enabling DNS support and hostnames.

- **Subnets**:
  - **Public Subnets**: Two public subnets in different availability zones for resources that require internet access.
  - **Private Subnets**: Two private subnets for internal resources that do not need public access.

- **Internet Gateway**: Facilitates communication between the VPC and the internet.

- **Route Tables**: Configures routing for the public subnets to direct traffic to the Internet Gateway.

- **Security Group**: Allows inbound HTTP traffic (port 80) from anywhere (0.0.0.0/0).

- **EC2 Instance**: Launches an EC2 instance using a specified Amazon Machine Image (AMI) within one of the public subnets.

## Features
- Scalable architecture with separate public and private subnets.
- Security group configured to allow web traffic.
- Outputs the public IP address of the EC2 instance for easy access.

## Technologies Used
- **AWS CloudFormation**: Infrastructure as code for deploying resources.
- **Amazon EC2**: Virtual server instances for hosting applications.

## Getting Started
### Prerequisites
- AWS Account
- AWS CLI installed and configured

## Create the CloudFormation stack

```
aws cloudformation create-stack \
  --stack-name MyTestStack \
  --template-body file:///path/to/Cloudforce-Challenge.yml \
  --capabilities CAPABILITY_NAMED_IAM


```


## To delete the stack

```
aws cloudformation delete-stack \
  --stack-name MyTestStack


```
