# Experiment 6 — Hosting a Static Website Using Amazon EC2

## Aim

To launch an EC2 instance and host a static website using Apache Web Server.

## Requirements

- AWS Account
- Internet Browser
- Amazon EC2 Instance
- Basic HTML File

## Services Used

- Amazon EC2
- Apache HTTP Server
- Amazon Linux 2

## Theory

Amazon EC2 (Elastic Compute Cloud) provides virtual servers in the cloud. A static website can be hosted on an EC2 instance by installing a web server such as Apache and storing HTML files in the web server's document root directory.

Architecture:

User → Internet → EC2 Public IP → Apache Web Server → HTML Page

## Procedure

1. Login to AWS Console.

2. Open Amazon EC2 service.

3. Launch a new EC2 instance:
   - Name → StaticWebServer
   - AMI → Amazon Linux 2
   - Instance Type → t2.micro

4. Create or select a key pair.

5. Configure network settings:
   - Allow SSH (Port 22)
   - Allow HTTP (Port 80)

6. Launch the instance.

7. Connect to the EC2 instance using EC2 Instance Connect.

8. Update the system:

   ```bash
   sudo yum update -y
