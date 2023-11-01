# 3-Tier-Architecture-with-AWS-CloudFormation

## VPC Stack

In this section, you'll find information about the resources defined in the AWS CloudFormation template for creating a Virtual Private Cloud (VPC) infrastructure and its associated components. The following are the key resources in the stack:

1. **VPC (Virtual Private Cloud)**:
   - [VPC](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-vpc.html) - The Virtual Private Cloud resource in the template.

2. **Internet Gateway**:
   - [Internet Gateway](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-internetgateway.html) - The Internet Gateway resource in the template.

3. **Subnets**:
   - [Subnet](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-subnet.html) - The Subnet resources in the template.

4. **Route Tables**:
   - [Route Table](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-routetable.html) - The Route Table resources in the template.

5. **NAT Gateway**:
   - [NAT Gateway](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-natgateway.html) - The NAT Gateway resource in the template.

6. **Elastic IP**:
   - [EIP](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-eip.html) - The Elastic IP resource in the template.

7. **VPC Gateway Attachment**:
   - [VPCGatewayAttachment](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-vpc-gateway-attachment.html) - The VPC Gateway Attachment resource in the template.

8. **Subnet Route Table Association**:
   - [SubnetRouteTableAssociation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-subnetroutetableassociation.html) - The Subnet Route Table Association resources in the template.

## EC2 Stack

In this section, you'll find information about the resources defined in the AWS CloudFormation template for deploying EC2 instances and an Application Load Balancer (ALB). The following are the key resources in the stack:

1. **Security Group for Test Server**:
   - [Security Group](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-securitygroup.html) - The security group for the Test Server in the template.
2. **Security Group for PHP Server 1**:
   - [Security Group](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-securitygroup.html) - The security group for PHP Server 1 in the template.

3. **EC2 Instance for Test Server**:
   - [EC2 Instance](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-instance.html) - The EC2 instance for the Test Server in the template.

4. **EC2 Instance for PHP Server 1**:
   - [EC2 Instance](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-instance.html) - The EC2 instance for PHP Server 1 in the template.

5. **EC2 Instance for PHP Server 2**:
   - [EC2 Instance](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-instance.html) - The EC2 instance for PHP Server 2 in the template.

6. **Application Load Balancer Security Group**:
   - [Security Group](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-securitygroup.html) - The security group for the Application Load Balancer (ALB) in the template.

7. **Application Load Balancer**:
   - [Application Load Balancer](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-elasticloadbalancingv2-loadbalancer.html) - The Application Load Balancer (ALB) resource in the template.

8. **Application Load Balancer Target Group**:
   - [Target Group](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-elasticloadbalancingv2-targetgroup.html) - The target group associated with the ALB in the template.

9. **Application Load Balancer Listener**:
   - [Listener](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-elasticloadbalancingv2-listener.html) - The listener for the ALB in the template.

## DB Stack

In this section, you'll find information about the resources defined in the AWS CloudFormation template for provisioning an Amazon RDS (Relational Database Service) instance. The following are the key resources in the stack:

1. **DB Subnet Group**:
   - [DB Subnet Group](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-rds-dbsubnetgroup.html) - The DB Subnet Group resource in the template used for RDS.

2. **Security Group for the RDS Instance**:
   - [Security Group](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-securitygroup.html) - The security group for the RDS instance in the template.

3. **Inbound Traffic Rule for RDS Security Group**:
   - [Security Group Ingress](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-ec2-security-group-ingress.html) - The inbound traffic rule for the RDS security group in the template.

4. **RDS Instance**:
   - [RDS Instance](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-rds-database-instance.html) - The RDS database instance in your template.

