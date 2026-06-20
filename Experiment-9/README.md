# Experiment 9 — Attaching Amazon EBS and Amazon EFS to an EC2 Instance

## Aim

To create and attach an Amazon Elastic Block Store (EBS) volume and an Amazon Elastic File System (EFS) to an EC2 instance.

## Requirements

- AWS Account
- Running Amazon EC2 Instance
- Amazon EBS
- Amazon EFS
- Internet Browser

## Services Used

- Amazon EC2
- Amazon EBS
- Amazon EFS
- Amazon Linux

## Theory

Amazon Elastic Block Store (EBS) provides block-level storage volumes that can be attached to EC2 instances and used like physical hard drives.

Amazon Elastic File System (EFS) provides scalable shared file storage that can be accessed by multiple EC2 instances using the Network File System (NFS). EFS requires NFS (TCP Port 2049) communication between the EC2 instance and the EFS mount target.

---

# Part A — Attaching an EBS Volume

## Procedure

1. Ensure that a running EC2 instance is available.

2. Open the Amazon EC2 Dashboard.

3. Navigate to:
   - Elastic Block Store
   - Volumes
   - Create Volume

4. Configure the EBS volume:
   - Size → 8 GB
   - Availability Zone → Same as the EC2 instance

5. Click Create Volume.

6. Select the created volume.

7. Click:
   - Actions
   - Attach Volume

8. Select the EC2 instance.

9. Specify the device name:
   ```
   /dev/xvdf
   ```

10. Click Attach.

11. Connect to the EC2 instance.

12. Verify the attached volume:

    ```bash
    lsblk
    ```

13. Format the volume:

    ```bash
    sudo mkfs -t ext4 /dev/xvdf
    ```

14. Create a mount directory:

    ```bash
    sudo mkdir /data
    ```

15. Mount the volume:

    ```bash
    sudo mount /dev/xvdf /data
    ```

16. Verify the mount:

    ```bash
    df -h
    ```

---

# Part B — Attaching Amazon EFS

## Procedure

17. Open the Amazon EFS Dashboard.

18. Click Create File System.

19. Select the required VPC.

20. Create the file system.

21. Ensure that the EFS Mount Target Security Group allows inbound NFS (TCP Port 2049) traffic from the EC2 instance Security Group.

22. Connect to the EC2 instance.

23. Install EFS utilities:

    ```bash
    sudo yum install -y amazon-efs-utils
    ```

24. Create a mount directory:

    ```bash
    sudo mkdir /efs
    ```

25. Mount the EFS file system:

    ```bash
    sudo mount -t efs fs-xxxxxxxx:/ /efs
    ```

26. Verify the mount:

    ```bash
    df -h
    ```

---

## Result

Successfully attached and mounted an Amazon EBS volume and an Amazon EFS file system to an EC2 instance.

## Screenshots

### EBS Volume Creation
Shows the creation of the Amazon EBS volume.

### EBS Volume Attachment
Shows the EBS volume attached to the EC2 instance.

### EBS Mount Verification
Shows the EBS volume successfully mounted.

### Amazon EFS Creation
Shows the creation of the Amazon EFS file system.

### EFS Mount Target Configuration
Shows the EFS mount target and network configuration.

### EFS Security Group Configuration
Shows the EFS security group configured to allow NFS (TCP Port 2049) traffic from the EC2 instance security group.

### EFS Mount Command
Shows the EFS file system being mounted on the EC2 instance.

### EFS Mount Verification
Shows the EFS successfully mounted and accessible.

## Learning Outcome

- Learned to create and attach Amazon EBS volumes to EC2 instances.
- Understood how to format and mount EBS storage.
- Learned to create and configure Amazon EFS.
- Understood the role of EFS mount targets and security groups.
- Learned that EFS uses the NFS protocol over TCP Port 2049.
- Gained practical experience in mounting shared network storage on EC2 instances.

## Cleanup

The EBS volume, EFS file system, and associated AWS resources were removed after completing the experiment to avoid unnecessary AWS usage charges.

## Troubleshooting

During the EFS mounting process, the following command was executed:

```bash
sudo mount -t efs fs-xxxxxxxx:/ /efs
```

Initially, the mount operation repeatedly failed with timeout errors:

```
Mount attempt 1/3 failed due to timeout after 15 sec.
Mount attempt 2/3 failed due to timeout after 15 sec.
```

To identify the cause, several configurations were verified:

* Confirmed that the Amazon EFS utilities were installed.
* Verified that the EFS mount targets were in the **Available** state.
* Checked that the EC2 instance and EFS were in the same AWS Region and VPC.
* Verified that the EC2 security group allowed NFS (TCP Port 2049) traffic.
* Reviewed the EFS mount target security group configuration.

The issue was found to be a security group mismatch. The EFS mount target security group allowed traffic from a different security group than the one attached to the EC2 instance.

The EFS security group inbound rule was updated to allow NFS (TCP Port 2049) traffic from the EC2 instance security group. After updating the source security group, the EFS file system mounted successfully.

This troubleshooting process provided practical experience in AWS networking, EFS mount targets, and security group configuration.
