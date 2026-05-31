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

9. Install Apache Web Server:

    ```bash
    sudo yum install httpd -y
    ```

10. Start and enable Apache:

    ```bash
    sudo systemctl start httpd
    ```
    ```bash
    sudo systemctl enable httpd
    ```

11. Navigate to the website directory:

    ```
    cd /var/www/html
    ```

12. Create the HTML webpage:

    ```bash
    sudo nano index.html
    ```

13. Save the HTML file.
14. Verify the website using the EC2 Public IPv4 address.
15. Create a Custom AMI:
    - Select the EC2 instance
    - Actions
    - Image and Templates
    - Create Image
16. Configure:
    - Image Name → Apache-WebServer-AMI
    - Description → AMI with Apache server and website

17. Click Create Image.
18. Wait for AMI status to change from Pending to Available.
19. Launch a new EC2 instance from the custom AMI.
20. Verify the website using the new instance public IP address.
    
## Result        
Successfully created a custom Amazon Machine Image (AMI) containing an Apache Web Server and hosted website, and launched a new EC2 instance using the created AMI.

## Screenshots


