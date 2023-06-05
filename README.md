# Terraforming  Azure Red Hat OpenShift(ARO) with GitHub Actions

![Terraforming Aro](/aro-terra-gitactions/assets/ARO-GitHubActions.png)

Deploying Azure RedHat Openshift with Terraform and Integrating with GitHub Actions
Terraforming  Azure Red Hat OpenShift(ARO) with GitHub Actions

# Introduction

By combining Infrastructure as Code with Continuous Integration and Continuous Delivery and/or Deployment  CI/CD  in cloud platforms, organizations can achieve a highly automated and streamlined software development and delivery process. Developers can use code to define and provision infrastructure resources, and use CI/CD to continuously integrate code changes and test the software. This approach can help organizations to achieve faster and more reliable software delivery, as well as improve the overall quality of their software.

# What will be covered

Many organizations use GitHub Actions and Terraform to deploy solutions in Azure as best practices to achieve collaboration, automation and scalability and security

In this blog post, we are going to learn how to deploy Azure Red Hat OpenShift (ARO) with Terraform and integrate it with Terraform Cloud and GitHub Actions.


If you want to learn about ARO you can get more information here.

Note: Azure-Samples/aro-azapi-terraform has been used for Terraform code as referenced in this post. 

# Prerequisites:

- Azure Account with active subscription

- Terraform Cloud account

- GitHub account

- Visual Studio Code + Git  + Azure CLI + Terraform CLI installed in local workstation

- Red Hat account  

To enhance the readability of this blog post, references to both the command-line interface (CLI) and graphical user interface (GUI) have been provided for creating resources.

# Steps:

- Install Azure CLI

xAzure CLI is a command-line interface for managing resources in Microsoft Azure, which is Microsoft's cloud computing platform

- Increase limits by VM series

Increasing limits by VM series for ARO installation is necessary to ensure that your ARO cluster has the resources it needs to operate efficiently and reliably. 
Standard DSv3 Family vCPUs = 150  
Total Regional vCPUs = 200

# Get a Red Hat pull secret

Navigate to your Red Hat OpenShift cluster manager portal and sign-in. Download the pull secret. We are going to use this secret in the Terraform Cloud while provisioning the ARO cluster. 

# Fork and Clone Github repository 

Fork the following repository in your GitHub account  and clone it in your local workstation.
https://github.com/DexHat/aro-terra-gitactions

After cloning in the local workstation update your .gitignore with following information.updated .gitignore file is part of repository.

# Secrets

pull-secret*
variables_secrets*

