# Terraform

Terraform is a universal approach where it **supports all cloud providers**. Terraform is provided by hashicorp. so we use hashicorp configuration language(HCL).

**cloud Formation only supports to AWS whereas terraform supports all providers.**


**Configuration File**: Terraform uses configuration files (often with a .tf extension) to define the desired infrastructure state. These files specify providers, resources, variables, and other settings. The primary configuration file is usually named **main.tf**, but you can use multiple configuration files as well.

To create main.tf refer in google as terraform aws

**Init**: **terraform init** initializes the terraform


**Plan**: A Terraform plan is a preview of changes that Terraform will make to your infrastructure. When you run **terraform plan**, Terraform analyzes your configuration and current state, then generates a plan detailing what actions it will take during the apply step.

**Apply**: The **terraform apply** command is used to execute the changes specified in the plan. It creates, updates, or destroys resources based on the Terraform configuration.

**Terraform lifecycle**

1.terraform init

2.terraform validate

3. terraform plan

4. terraform apply

5. terraform destroy

**main.tf** : it is a main configuration file wehere resources are defined

**variables.tf** : it is a file used to define variables which are used in configuration file

**Outputs.tf** : it is a file to define output values after terraform apply. outputs allow terraform to display key information after the resources are created or updated.

**eg:**

output "instance_id"{

  description = "The ID of the ec2 instance"
  
  value = aws_instance.example.id          (# here example is written in main.tf)
  
  }

output "public_ip"{

  description = "The public ip address of ec2 instance"
  
  value = aws_instance.example.public.ip
  
  }
  


**providers.tf**: file to configure terraform providers

**terraform.tfvars** : this file overrides the variable.tf file

**terraform apply --auto-approve** which will apply without asking any yes r no prompt

**terraform destroy** will destroy or removes the created resources which r generated from apply command

**-->** when we run **terraform init** command it generates hidden files .terraform and .terraform.lock.hcl file where in lock file it will be a dependencies and libraries , provider versions which we have provided in main.tf 

**terraform.tfstate** : in this statefile metadata will be stored . whenever if we do modification in main.tf file it will look into i.e plan look into statefile whether there are changes or not and then only apply command will work.

**-->** we store configuration files in github whereas we store **statefile** in s3 bucket or terraform workspaces

**modules**: These are reusable in managing complex systems. Each module typically contains its own main.tf, variables.tf, outputs.tf 

**Dynamic Blocks**: where multiple items can be created within a resouce. for ex in ec2 , to define security groups, vpc , auto scaling we use dynamic blocks. "ingress" means inbound traffic and "egress" means outbound traffic. we'll define the values in varaibles.tf and will call in to main.tf by using **for_each**
