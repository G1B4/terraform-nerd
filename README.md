# Introduction to Terraform Modules

This repository contains all the materials for a presentation on Terraform Modules. Slides for the talk are provided in a PDF.

Each example consists of several drafts and final code.

## Example 1

Basic  `terraform`  script to create an EC2 instance in AWS.

**draft1** With one command create an EC2 instance hardcoding all the information.

**draft2** Introduce variables and outputs in the single file script.

**final** Split the inputs, outputs, and resources into 3 files and add a data source resource to get information about the default vpc in order to create a security group for the EC2 instance.

## Example 2

Building on the previous example we start creating re-usable modules. A security group module is introduced as well. 

**draft1** Start by building 2 modules to create an EC2 instance and a security group respectively. The security group module has its rules hard coded in the file. Rewrite `example1/final` using these modules.

**draft2** Rewrite the security group module to abstract the ingress and egress rules so they can be specified parametrically in the calling script. Add one more instance and one more security group to the mix.


### Tips

- To format a Terraform file run in the directory that contains the files:
```bash
terraform fmt
```
- To format all the files for the rut and child directories execute:
```bash
find . -type d -exec terraform fmt '{}' \;
```
