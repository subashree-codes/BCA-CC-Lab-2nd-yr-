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
   ```

9. Install Apache Web Server:

   ```bash
   sudo yum install httpd -y
   ```

10. Start Apache service:

    ```bash
    sudo systemctl start httpd
    ```

11. Enable Apache service:

    ```bash
    sudo systemctl enable httpd
    ```

12. Verify Apache status:

    ```bash
    sudo systemctl status httpd
    ```
   
13. Navigate to:  
     cd /var/www/html

14. Create and save the HTML file.

15. Copy the EC2 public IPv4 address.
    
16. Open the public IP address in a browser.
    
## Result

Successfully hosted a static website on an Amazon EC2 instance using Apache Web Server.

## Screenshots    

### Security Group Configuration
Shows SSH and HTTP ports enabled in the security group.

### EC2 Instance Running
Shows the EC2 instance in running state.

### Apache Terminal Access
Shows successful connection to the EC2 instance terminal.

### Apache Installation Commands - Part 1
Shows commands used to update the system and install Apache Web Server.

### Apache Installation Commands - Part 2
Shows commands used to start, enable, and verify the Apache service.

### HTML Webpage Source Code
Shows the HTML code created inside index.html for hosting the webpage on the EC2 instance.

### Hosted Website Output
Shows the static website hosted on the EC2 instance and accessed through the public IP address.

## Learning Outcome
  - Learned how to launch and configure an EC2 instance.
  - Understood Apache Web Server installation and management.
  - Learned how to host a static website on EC2.
  - Gained hands-on experience with cloud-based web hosting.

## Cleanup

The EC2 instance was stopped and terminated after completing the experiment to avoid unnecessary AWS usage charges.
