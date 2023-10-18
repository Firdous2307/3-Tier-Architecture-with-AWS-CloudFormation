# AWS-Networking-Projects Using AWS CloudFormation

| Layer | AWS Resource | Description |
|-------|--------------|-------------|
| 1. Physical Layer(VPC) | `AWS::EC2::VPC` | The foundational layer that defines the physical infrastructure, such as the VPC (Virtual Private Cloud). |
| 2. Data Link Layer (VPC and Subnets) | `AWS::EC2::Subnet` | Manages data organization on the network, including the creation of subnets within the VPC. |


# CloudFormation VPC Deployment :cloud:

This repository contains an AWS CloudFormation template for creating a Web Application
## Parameters :gear:

- `VpcCidrBlock` (Default: 10.0.0.0/16): Specifies the CIDR block for the VPC.
- `Az1` (Default: us-east-2a): Sets the default Availability Zone for the VPC.
- `SubnetCidrBlocks`: A list of CIDR blocks for subnets.
- `Az2` (Default: us-east-2b): Additional Availability Zone for subnets.
- `Az3` (Default: us-east-2c): Another Availability Zone for subnets.

## Resources :building_construction:

### MyVPC
- Type: AWS::EC2::VPC
- Properties: 
  - `CidrBlock`: Uses the `VpcCidrBlock` parameter value.
  - `EnableDnsSupport` and `EnableDnsHostnames` are enabled.
  - A tag with the VPC name.

### PublicSubnet1, PublicSubnet2, PublicSubnet3
- Type: AWS::EC2::Subnet
- Properties: 
  - `AvailabilityZone`: References the `Az1`, `Az2`, and `Az3` parameters.
  - `CidrBlock`: Selects CIDR blocks from `SubnetCidrBlocks`.
  - `VpcId`: References the `MyVPC`.
  - Tags with subnet names.


# CloudFormation Deployment Script Guide :rocket:

This guide provides an explanation of the Bash script for deploying CloudFormation stacks along with a TOML configuration file. Make sure to follow these steps to set up your deployment process.

## Prerequisites :wrench:

Before you begin, ensure that you have the following prerequisites:

- [AWS CLI](https://aws.amazon.com/cli/) installed and configured with your AWS credentials.
- [toml-cli](https://www.npmjs.com/package/toml-cli) installed. You can install it using `npm install -g toml-cli`.
