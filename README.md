# Terraform AWS EC2 Infrastructure Provisioning

This project demonstrates how to provision cloud infrastructure on AWS using Terraform as Infrastructure as Code (IaC). The configuration automatically deploys an EC2 instance with an SSH-enabled security group, allowing secure remote access to the server.

The infrastructure created in this project can also be extended by integrating Ansible for server configuration and application deployment. An example Ansible setup for this workflow is available in [Ansible Configuration Repository](https://github.com/mishalbiju07/Configuration-Management).

## Project Overview

This Terraform configuration performs the following tasks:

1. Configures the AWS provider

2. Creates a security group allowing SSH access (port 22)

3. Launches an EC2 instance

4. Outputs the public IP address of the created instance

This project demonstrates the foundational workflow of automated cloud infrastructure provisioning using Terraform.

## Tech Stack

- Terraform

- AWS EC2

- AWS Security Groups

- AWS CLI

- Infrastructure as Code (IaC)

## Optional integration:

Ansible (for server configuration and automation)

## Infrastructure Components
1. AWS Provider

- The AWS provider is configured to deploy resources in the ap-south-1 (Mumbai) region.

2. Security Group

- A security group named allow_ssh is created with the following rules:

3. Ingress

- Port: 22

- Protocol: TCP

- Source: 0.0.0.0/0 (allows SSH access from anywhere)

4. Egress

- Allows all outbound traffic.

5. EC2 Instance

- An EC2 instance is provisioned with the following configuration:

- Instance Type: t3.micro

- AMI: Ubuntu image

- Key Pair: "*Your keypair name*"

- Security Group: allow_ssh

6. Output

- After successful deployment, Terraform outputs the public IP address of the EC2 instance, which can be used to connect via SSH.

## Project Structure
```
.
├── main.tf
└── README.md
```
## Prerequisites

### Before running this project, ensure the following are installed and configured:

- Terraform

- AWS CLI

- AWS Account

- AWS credentials configured locally

- Configure AWS credentials
- aws configure

## Usage
### Initialize Terraform
```terraform init```
### Preview Infrastructure Changes
```terraform plan```
### Apply Configuration
```terraform apply```

- Confirm with yes when prompted.

## Once the deployment is complete, Terraform will output the public IP address of the EC2 instance.

## Connecting to the Server
```ssh -i linuxserver.pem ubuntu@<public_ip>```
## Destroy Infrastructure

### To remove all created resources:

``` terraform destroy ```
## Purpose

This project was built as part of learning DevOps practices and Infrastructure as Code, demonstrating how Terraform can automate cloud infrastructure provisioning on AWS.
