# 3-Tier-Architecture-with-AWS-CloudFormation

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

### PublicSubnets, PrivateSubnets, PrivateDBSubnets
- Type: AWS::EC2::Subnet
- Properties: 
  - `AvailabilityZone`: References the `Az1`, `Az2`, and `Az3` parameters.
  - `CidrBlock`: Selects CIDR blocks from `SubnetCidrBlocks`.
  - `VpcId`: References the `MyVPC`.
  - Tags with subnet names.


# CloudFormation Deployment Script Guide :rocket:

This guide provides an explanation of the Bash script for deploying CloudFormation stacks along with a envfile. Make sure to follow these steps to set up your deployment process.

## Prerequisites :wrench:

Before you begin, ensure that you have the following prerequisites:

- [AWS CLI](https://aws.amazon.com/cli/) installed and configured with your AWS credentials.

``` sh
aws ec2 describe-images --filters "Name=name,Values=amzn2-ami-hvm-2.0.*" "Name=state,Values=available" --query 'Images[0].ImageId' --output text
```

Fixed the SubnetCidrBlocks parameter to include the CIDR blocks as a single string.
Corrected the RoutetoNATGW1 and RoutetoNATGW2 to use `NatGatewayId` instead of `GatewayId` to specify the NAT Gateway.

*Note*: NAT Gateways in AWS are immutable, which means you cannot directly update them. If you need to make changes to a NAT Gateway, you typically need to create a new one and update your route tables to use the new NAT Gateway.


In AWS CloudFormation, when you define NetworkInterfaces for an EC2 instance, you shouldn't specify SecurityGroupIds in the Properties of the instance resource.

I do not know why I keep getting an error anyime i try to **AssociatePublicIpAddress** for my `TestServerInstance``. I have a Public Subnet, so i am thinking, I do not need to assign it, it will automatically do that for me, but no it does not. 

Okay, so the issue was not enabling public IP address for my subnet, Fixed that already.