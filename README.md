# Build, change, and destroy AWS infrastructure using Terraform.

[/] Make sure to have AWS account setup
  - Install AWS CLI
  - Configure AWS credentials

[/] Write Terraform configuration to launch a single AWS instance

[/] Initialize directory
  - terraform init

[/] Format and validate the configuration
  - terraform fmt
  - terraform validate

[/] Create an AWS EC2 instance
  - terraform apply run in the same directory as `main.tf`

[/] Inspect newly created AWS EC2 instance
  - terraform show

[/] Change Infrastructure

[/] Destroy newly created AWS EC2 instance

[/] Define input variables

## Questions, comments, concerns, etc:

### What is known as Terraform's _configuration_?
Terraform considers a _configuration_ as the set of files that is used to describe Terraform infrastructure.

### Terraform Block
The `terraform {}` block is necessary so that Terraform knows which _provider_ to download from the [Terraform Registry](https://registry.terraform.io/). In the example configuration, the provider was for `aws`.

### Provider Block
The `provider{}` block configures a provider (in the example we used `aws`) that creates or manages the resources for the instance. A **provider** is a Terraform plugin which integrates with the API from the service (`aws`).

Multiple providers can be set from different providers. Multiple providers can be used together as well.

### Profile Attribute
The `profile =""` attribute in the example refers Terraform to the AWS credentials stored locally.

### Resource Block
The `resource` block defines a part of the infrastructure. An example of a resource is an EC2 instance or a Heroku application (physical or logical).

The arguments for the resource block can define machine sizes, disk image names, VPC IDs, etc. The [providers reference documents](https://www.terraform.io/docs/providers/index.html) shows required and optional arguments for each resource provider (`aws` in the example).

In the example, a EC2 instance is being created with a specified AMI for Ubuntu as a `t2.micro` instance which falls under the free AWS tier.
