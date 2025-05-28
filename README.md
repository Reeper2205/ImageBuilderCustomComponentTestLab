# ImageBuilderCustomComponentTestLab
This CloudFormation template sets up an AWS Image Builder environment for creating and managing custom AMIs (Amazon Machine Images). Here's a breakdown of its main components:

    Network Infrastructure:

    Creates a VPC with public and private subnets
    Sets up NAT Gateway for private subnet internet access
    Configures Internet Gateway for public subnet
    Creates necessary route tables and associations

    Security Components:

    Security group for Image Builder instances
    S3 bucket for logs with versioning and public access blocking
    IAM roles and instance profile with necessary permissions

    Image Builder Pipeline Configuration:

    Creates an Image Builder pipeline that:
        Uses Amazon Linux 2 as the base image
        Adds a simple custom component that outputs a test message
        Configures infrastructure settings (using t2.micro instances)
        Sets up distribution settings for the resulting AMI

    Launch Template:

    Creates an EC2 launch template for the resulting AMI
    Configures t3.micro as the instance type
    Includes basic user data script

    Key Components:

    ImageRecipe: Defines the base image and components to be used
    ImageComponent: Contains the build steps for customizing the image
    InfrastructureConfiguration: Specifies where and how to build the image
    DistributionConfiguration: Defines how the resulting AMI should be distributed



