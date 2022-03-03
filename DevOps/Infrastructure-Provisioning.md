# Infrastructure Provisioning

## Overview

This goes in line with Containers and Container Orchestration. Tools like **Terraform** are used to actually take your container clusters and deploy those resources onto popular cloud service providers instances. It's an IaC tool.

An example of a Terraform .tf file is as follows:

<!-- This isn't actually C#, but a Terraform file. main.tf -->
```C#
provider "aws" {}

variable cidr_blocks {}
variable avail_zone {}

resource "aws_vpc" "myapp-vpc" {
  cidr_block = var.cidr_blocks[0].cidr_block
  tags = {
    Name: var.cidr_blocks[0].name
  }
}
```
