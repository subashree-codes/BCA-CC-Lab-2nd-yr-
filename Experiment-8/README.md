# Experiment 8 — Allocating an Elastic IP Address to an EC2 Instance

## Aim

To allocate and associate a new Elastic IP address to an EC2 instance using the AWS Management Console.

## Requirements

- AWS Account
- **Running** EC2 Instance
- Internet Browser

## Services Used

- Amazon EC2
- Elastic IP

## Theory

An Elastic IP address is a static public IPv4 address provided by AWS. Unlike normal public IP addresses that may change when an instance is stopped and started, an Elastic IP remains constant and can be reassigned to different EC2 instances when required.

Elastic IPs are commonly used for:
- Hosting websites
- Remote server access
- Applications requiring a fixed public IP address

## Procedure

1. Login to AWS Console.

2. Open Amazon EC2 service.

3. In the left navigation pane, select:
   - Network & Security
   - Elastic IPs

4. Click:
   - Allocate Elastic IP Address

5. Keep default settings.

6. Click Allocate.

7. Select the newly allocated Elastic IP address.

8. Click:
   - Actions
   - Associate Elastic IP Address

9. Configure association:
   - Resource Type → Instance
   - Select running EC2 instance
   - Select private IP address

10. Click Associate.

11. Open:
    - EC2 Dashboard
    - Instances

12. Verify that the Elastic IP address is attached to the EC2 instance.

## Result

Successfully allocated and associated an Elastic IP address with an EC2 instance using the AWS Management Console.

## Screenshots

### EC2 Instance Running
Shows the EC2 instance in running state before Elastic IP allocation.

### Elastic IP Dashboard
Shows the Elastic IP section in the EC2 console.

### Allocate Elastic IP Address
Shows allocation of a new Elastic IP address.

### Elastic IP Allocated
Shows the newly created Elastic IP address.

### Associate Elastic IP Configuration
Shows the Elastic IP association settings.

### Instance Selection
Shows the EC2 instance selected for Elastic IP association.

### Elastic IP Associated Successfully
Shows successful association of the Elastic IP with the EC2 instance.

### Verification in EC2 Instance
Shows the Elastic IP attached to the EC2 instance as its public IPv4 address.

## Learning Outcome

- Learned how Elastic IP addresses work in AWS.
- Understood the difference between dynamic and static public IP addresses.
- Learned how to allocate and associate Elastic IPs with EC2 instances.
- Gained hands-on experience with EC2 networking.


## Cleanup

The Elastic IP address was released and EC2 resources were removed after completing the experiment to avoid unnecessary AWS usage charges.
