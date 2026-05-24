# Experiment 3 — Hosting a Static Website Using AWS S3

## Aim

To create and host a static website using Amazon S3 (Simple Storage Service).

## Requirements

- AWS Account
- Internet Browser
- Basic HTML file (index.html)

## Services Used

- Amazon S3
- Static Website Hosting

## Theory

Amazon S3 (Simple Storage Service) allows users to host static websites by storing HTML, CSS, JavaScript, and image files inside an S3 bucket and enabling public access.

Static websites do not require a backend server and can be accessed directly through a public URL.

## Procedure

1. Login to AWS Console.

2. Open Amazon S3 service.

3. Click **Create Bucket**.

4. Configure Bucket Settings:
   - Bucket type → General Purpose
   - Bucket namespace → Global Namespace
   - Bucket name → Unique bucket name

5. Configure Additional Settings:
   - Object Ownership → ACLs Enabled
   - Bucket Versioning → Enabled
   - Encryption → SSE-S3

6. Disable:
   - Block all public access

7. Create the bucket.

8. Open the bucket and upload:
   - index.html
   - CSS files (optional)
   - Images (if any)

9. Go to:
   - Properties → Static Website Hosting
   - Enable static website hosting.

10. Set:
    - Index document → index.html

11. Configure Bucket Policy for public access.
    - Go to Permissions → Bucket Policy
    - Paste this policy (replace bucket name)

    {
     "Version": "2012-10-17", 
     "Statement": [
        {
        "Effect": "Allow", 
        "Principal": "*", 
        "Action": "s3:GetObject", 
        "Resource": "arn:aws:s3:::my-static-web-123/*" 
        }
      ]
    }  
    - Click Save.
   
12. Copy the static website endpoint URL. 

13. Open the URL in browser to access the hosted website.

## Result

Successfully hosted a static website using Amazon S3 and accessed it through a public URL.

## Screenshots

### S3 Dashboard
Shows the Amazon S3 dashboard.

### Create Bucket Configuration
Shows bucket creation settings and public access configuration.

### Website File Upload
Shows HTML and website files uploaded into the S3 bucket.

### Static Website Hosting
Shows static website hosting enabled for the bucket along with the generated website endpoint URL.

### Bucket Policy
Shows bucket policy configured for public access.

### Website Endpoint
Shows the generated static website endpoint URL.

### Hosted Website Output
Shows the hosted website opened successfully in browser.

## Learning Outcome

- Learned how to create and configure an S3 bucket.
- Understood static website hosting using Amazon S3.
- Learned how public bucket access works in AWS.
- Gained hands-on experience in cloud-based website hosting.

## Note

Public access was enabled only for educational static website hosting purposes.

## Cleanup

After completing the experiment, the S3 bucket contents were emptied and the bucket was deleted to avoid unnecessary AWS resource usage.
