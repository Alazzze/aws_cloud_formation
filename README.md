# AWS CloudFormation Template: VPC, EC2, and ALB with nginx

This CloudFormation template creates a Virtual Private Cloud (VPC) with two public subnets, an EC2 instance running nginx, and an Application Load Balancer (ALB) distributing traffic to the EC2 instance.

## Overview

The CloudFormation template consists of the following resources:

- **VPC:** A Virtual Private Cloud with a CIDR block of `10.0.0.0/16`.
- **Subnets:** Two public subnets (`10.0.1.0/24` and `10.0.2.0/24`) spanning across availability zones.
- **Internet Gateway:** Attached to the VPC to allow outbound internet access.
- **Route Table:** Configured to route internet traffic through the Internet Gateway.
- **EC2 Instance:** An Amazon Linux EC2 instance running nginx in one of the public subnets.
- **Security Group:** Allows inbound traffic on ports 80 (HTTP) and 22 (SSH) from anywhere.
- **ALB:** An Application Load Balancer configured for internet-facing traffic, distributing requests to the EC2 instance.
- **Target Group:** Associated with the ALB to direct traffic to the EC2 instance.

## Usage

To deploy this CloudFormation template:

1. Make sure you have the AWS CLI installed and configured with appropriate permissions.
2. Clone this repository to your local machine.
3. Navigate to the directory containing the CloudFormation template.
4. Run the following AWS CLI command to create the stack:

aws cloudformation create-stack --stack-name MyStackName --template-body
file://cloudformation.yml --capabilities CAPABILITY_IAM



Replace `MyStackName` with your desired stack name.

## Cleanup

To delete the stack and all associated resources, run the following AWS CLI command:

aws cloudformation delete-stack --stack-name MyStackName


Replace `MyStackName` with the name of the stack you created.

## License

This project is licensed under the [MIT License](LICENSE).
