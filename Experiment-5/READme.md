# Experiment 5 — Transfer Data Across AWS Regions Using Amazon S3

## Aim

To transfer data across AWS regions using Amazon S3 Cross-Region Replication (CRR).

## Requirements

- AWS Account
- Amazon S3 Buckets
- Internet Browser
- Sample file for upload

## Services Used

- Amazon S3
- S3 Cross-Region Replication (CRR)
- AWS IAM

## Theory

Amazon S3 Cross-Region Replication (CRR) automatically replicates objects from a source bucket in one AWS region to a destination bucket in another AWS region.

CRR helps in:
- Disaster recovery
- Backup management
- Low-latency access
- Cross-region data availability

Example Data Flow:

Source Bucket (Mumbai Region)  
↓  
AWS Replication  
↓  
Destination Bucket (US Region)

Versioning must be enabled in both buckets for replication to work.

## Procedure

1. Login to AWS Console.

2. Open Amazon S3 service.

3. Create Source Bucket:
   - Unique bucket name
   - Region → Asia Pacific (Mumbai)

4. Create Destination Bucket:
   - Unique bucket name
   - Region → US East (N. Virginia)

5. Open both buckets.

6. Enable Bucket Versioning:
   - Go to Properties
   - Enable Versioning

7. Open the Source Bucket.

8. Go to:
   - Management
   - Replication Rules

9. Click:
   - Create Replication Rule

10. Configure replication settings:
    - Select destination bucket
    - Choose destination AWS region

11. Allow AWS to automatically create the IAM replication role.

12. Save the replication rule.

13. Upload a file to the source bucket.

14. Wait for replication process.

15. Open the destination bucket and verify that the file is replicated successfully.

## Observation

The uploaded file in the source bucket was automatically replicated to the destination bucket located in another AWS region.

## Result

Successfully transferred data across AWS regions using Amazon S3 Cross-Region Replication.

## Screenshots

### Source and Destination Bucket Creation
Shows creation of the source bucket in Mumbai region and destination bucket in US region.

### Bucket Versioning
Shows versioning enabled for both S3 buckets.

### Replication Rule Configuration
Shows Cross-Region Replication rule configuration.

### IAM Role Creation
Shows AWS IAM role automatically created for replication.

### File Upload in Source Bucket
Shows file uploaded into the source bucket.

### Replicated File in Destination Bucket
Shows replicated file successfully appearing in the destination bucket.

## Learning Outcome

- Learned how Cross-Region Replication works in Amazon S3.
- Understood the importance of bucket versioning.
- Learned how AWS IAM roles are used in replication.
- Gained hands-on experience in transferring data across AWS regions.

## Cleanup

Replication rules, uploaded files, and S3 buckets were removed after completing the experiment to avoid unnecessary AWS usage charges.
