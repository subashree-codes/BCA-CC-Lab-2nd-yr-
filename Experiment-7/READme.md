# Experiment 7 — Creating a Custom Amazon Machine Image (AMI)

## Aim

To create a custom Amazon Machine Image (AMI) with Apache Web Server and a hosted website using AWS EC2.

## Requirements

- AWS Account
- Amazon EC2 Instance
- Internet Browser
- Basic HTML File

## Services Used

- Amazon EC2
- Amazon Machine Image (AMI)
- Apache HTTP Server
- Amazon Linux

## Theory

An Amazon Machine Image (AMI) is a pre-configured template that contains the operating system, application software, and configuration settings required to launch an EC2 instance.

Creating a custom AMI allows users to quickly launch multiple instances with identical configurations without repeating setup steps.

## Procedure

1. Login to AWS Console.

2. Open Amazon EC2 service.

3. Launch a new EC2 instance:
   - Name → Apache-Server
   - AMI → Amazon Linux
   - Instance Type → t2.micro

4. Create or select a key pair.

5. Configure Security Group:
   - Allow SSH (Port 22)
   - Allow HTTP (Port 80)

6. Launch the instance.

7. Connect to the EC2 instance using EC2 Instance Connect.

8. Update the system:

   ```bash
   sudo yum update -y
   ```
