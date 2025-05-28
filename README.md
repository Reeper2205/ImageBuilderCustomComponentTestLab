# ImageBuilderCustomComponentTestLab
This CloudFormation template creates a Windows-based test environment, specifically designed for AWS Test Orchestrator for EC2 (TOE). Here's a breakdown of its main components:

    Network Infrastructure:

    VPC with CIDR 10.0.0.0/16
    Public subnet (10.0.1.0/24)
    Private subnet (10.0.2.0/24)
    NAT Gateway and Internet Gateway
    Appropriate route tables for both subnets

    Security:

    Security group allowing only port 443 traffic (inbound and outbound)
    IAM role with SSM managed policy
    Instance profile for EC2

    EC2 Instance:

    Windows Server 2019 instance (t3.medium)
    50GB GP2 EBS volume
    Placed in the private subnet
    Uses latest Windows AMI from SSM Parameter Store

    UserData Script (PowerShell):

    Creates a TOE directory (C:\TOE)
    Creates a YAML component file for EC2 Image Builder
    Downloads AWS TOE executable
    Creates a test file on the desktop
    Sets up basic configuration for TOE testing

    Important Security Features:

    Instance is in private subnet (no direct internet access)
    Access managed through Systems Manager (SSM)
    Restricted security group rules



