# Terraform

Terraform is a universal approach where it supports all cloud providers. Terraform is provided by hashicorp. so we use hashicorp configuration language(HCL).

**Configuration File**: Terraform uses configuration files (often with a .tf extension) to define the desired infrastructure state. These files specify providers, resources, variables, and other settings. The primary configuration file is usually named **main.tf**, but you can use multiple configuration files as well.

To create main.tf refer in google as terraform aws

**Init**: **terraform init** initializes the terraform


**Plan**: A Terraform plan is a preview of changes that Terraform will make to your infrastructure. When you run **terraform plan**, Terraform analyzes your configuration and current state, then generates a plan detailing what actions it will take during the apply step.

**Apply**: The **terraform apply** command is used to execute the changes specified in the plan. It creates, updates, or destroys resources based on the Terraform configuration.

**Terraform lifecycle**

1.terraform init

2. terraform plan

3. terraform apply

4. terraform destroy
