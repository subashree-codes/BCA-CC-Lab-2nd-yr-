# Experiment 2 — Launching a MySQL Database Using Amazon RDS

## Aim

To create and launch a MySQL database using Amazon RDS in AWS cloud environment.

## Requirements

- AWS Account
- Internet Browser
- Basic SQL knowledge

## Services Used

- Amazon RDS
- MySQL Database Engine

## Theory

Amazon RDS (Relational Database Service) is a cloud database service provided by AWS. It allows users to create and manage databases without installing or maintaining database software manually.

RDS automatically handles:
- Backup
- Security
- Maintenance
- Scaling

  ## Procedure

1. Login to AWS Console.

2. Open:
   - Aurora and RDS
   - RDS Dashboard

3. Click **Create Database**.

4. Select:
   - Standard Create
   - Engine Type → MySQL

5. Choose Template:
   - Free Tier

6. Configure DB Instance:
   - DB instance identifier
   - Master username
   - Create a custom password

7. DB Instance Settings:
   - Instance class → db.t3.micro
   - Storage → Default allocated storage

8. Connectivity Settings:
   - Public Access → Yes
   - VPC → Default
   - Allow inbound traffic

9. Additional Configuration:
   - Initial database name (optional)

10. Click **Create Database**.

11. Wait until database status becomes **Available**.

## Result

Successfully created and launched a MySQL database instance using Amazon RDS service in AWS cloud environment.

## Screenshots

### RDS Dashboard
Shows the Amazon RDS dashboard in AWS Console.

### MySQL Engine Selection
Shows MySQL selected as the database engine.

### Database Configuration
Shows database instance and connectivity settings.

### Database Status
Shows the RDS database instance in Available state.

## Learning Outcome

- Learned how to create a cloud database using Amazon RDS.
- Understood basic MySQL database configuration in AWS.
- Learned about DB instance settings and connectivity options.
- Gained hands-on experience with AWS database services.

## Note

The database instance was stopped/deleted after the experiment to avoid unnecessary AWS Free Tier usage charges.
