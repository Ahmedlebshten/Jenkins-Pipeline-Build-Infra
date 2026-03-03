# Jenkins Pipeline – Automating AWS Infrastructure with Terraform

This repository contains the Terraform code and Jenkins pipeline used to automate the provisioning of AWS infrastructure.
The pipeline pulls the code from GitHub, runs Terraform steps, and builds the infrastructure automatically.

____

## Project Structure:
```
.
├── modules/                # Reusable Terraform modules  
├── Jenkinsfile             # Jenkins pipeline to automate infra deployment
├── backend.tf              # Remote backend configuration (S3)
├── main.tf                 # Main infrastructure definitions
├── providers.tf            # AWS provider configuration
├── variables.tf            # Variables definitions
├── outputs.tf              # Output values
├── terraform.tfvars        # Variables values (excluded from repo if sensitive)
├── .gitignore
└── README.md
```
## What This Pipeline Does:

#### The Jenkins pipeline automates the full Terraform workflow:
- Checkout code from GitHub
- Terraform Init (backend + plugins)
- Terraform Plan (preview changes)
- Terraform Apply (provision AWS infrastructure)

No manual AWS Console interaction is needed — everything is done through code.

____

## Tech Stack:
- Jenkins
- Terraform
- AWS
- GitHub

____

## Purpose of This Pipeline:

#### This repository represents Pipeline 1 of a larger DevOps project:
- Infrastructure Pipeline (this repo)
- CI Pipeline (Docker build + image push)
- GitOps Deployment using ArgoCD

This pipeline lays the foundation by deploying the underlying AWS infrastructure automatically.

____

## How to Run:
- Add AWS credentials to Jenkins
- Configure a Jenkins job pointing to this repository
- Run the pipeline — Jenkins will build the entire AWS environment
