# Automated Container Deployment on Microsoft Azure

**Module:** Networks and Systems Administration  
**Student:** Syed Mubashir Ahmed Hashmi  
**Student ID:** 20089221  

---

## Project Title

**Automated Cloud Infrastructure Deployment using Terraform, Ansible, and Docker on Microsoft Azure**

---

## Project Goal

Build a complete cloud automation pipeline that automatically:

- Creates infrastructure
- Configures a virtual machine
- Deploys a containerized web application
- Makes the application accessible in a browser

All processes are fully automated using **Infrastructure as Code** and **configuration management**.

---

## Overview

This project demonstrates a real-world cloud automation system that provisions infrastructure, configures a server, and deploys a web application automatically on Microsoft Azure.  

The entire setup was completed on a **Windows environment** using free and open-source tools including:

- Terraform
- Ansible
- Docker
- Node.js
- Azure CLI
- GitHub

The system eliminates manual setup and ensures **consistent, repeatable deployments**.

---

## Automation Pipeline

Windows Machine → Terraform → Azure Virtual Machine → Ansible → Docker Container → Browser

---

## Tools and Purpose

### Terraform
Creates Azure infrastructure including:

- Resource Group
- Virtual Network
- Subnet
- Network Security Group
- Public IP
- Linux Virtual Machine

### Ansible
Connects to the Azure virtual machine via SSH and:

- Installs Docker
- Configures system packages
- Deploys application container

### Docker + Node.js
Runs the web application inside a **lightweight containerized environment**, ensuring consistent runtime across deployments.

### Azure CLI
Authenticates with Azure and allows Terraform to interact with cloud resources.

### Git and GitHub
Used for version control, project storage, and tracking deployment changes.

---

## Step-by-Step Setup and Commands

### 1️ Generate SSH Key (Windows PowerShell)

This key allows secure connection to the Azure virtual machine.

ssh-keygen -t rsa -b 4096

Public key is used by Terraform for VM access.

### 2️ Login to Azure

Authenticate your Azure account.

az login

Browser will open → login successful.

### 3️ Terraform — Build Infrastructure

Navigate to Terraform directory:

cd terraform

Initialize Terraform:

terraform init

Preview infrastructure plan:

terraform plan

Create infrastructure:

terraform apply

View created resources:

terraform show
terraform state list

### 4️ Connect to Virtual Machine

Use public IP from Terraform output.

ssh azureuser@20.100.182.186

### 5️  Ansible — Configure Server

Check connection:

ansible -i inventory.ini all -m ping

Run playbook to install Docker and deploy container:

ansible-playbook -i inventory.ini playbook.yml

### 6️  Docker Application

Verify container running:

docker ps

Test web application locally on VM:

curl http://localhost

### Live Application

Access the deployed web application here:

👉 http://20.100.182.186:8080/

The website is deployed automatically through full cloud automation.

## Verification Commands (For Demonstration)

Terraform Resources
terraform state list
terraform show
Ansible Connectivity
ansible all -m ping -i inventory.ini
Docker Status
docker ps
Application Response
curl http://localhost

## Key Features

✔ Infrastructure as Code
✔ Automated server configuration
✔ Containerized deployment
✔ Secure SSH access
✔ Public web access
✔ Fully repeatable deployment
✔ No manual configuration

## Learning Outcomes

This project demonstrates practical understanding of:

Cloud infrastructure provisioning

Configuration management

Containerization

Automation pipelines

DevOps workflow

Azure cloud services

## Conclusion

This project successfully implemented an end-to-end automated cloud deployment pipeline on Microsoft Azure.

Infrastructure provisioning, system configuration, and application deployment were fully automated using Terraform, Ansible, and Docker.

The system ensures consistent, reliable, and repeatable cloud deployments without manual intervention.

## Author

Syed Mubashir Ahmed Hashmi
MSc Information Systems