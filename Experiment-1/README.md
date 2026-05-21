# Experiment 1 — Launching Linux and Windows VMs using AWS EC2

## Aim

To create and launch Linux and Windows virtual machines using Amazon EC2 service in AWS Cloud.

## Requirements

* AWS Account
* Internet Browser
* Basic knowledge of cloud computing

## Services Used

* Amazon Web Services EC2
* Amazon Linux AMI
* Windows Server AMI

## Procedure

### Launching Linux VM

1. Login to AWS Console
2. Open EC2 Dashboard
3. Click **Launch Instance**
4. Enter instance name: `Linux-VM`
5. Choose AMI:
   * Amazon Linux (Free Tier Eligible)
     
6. Select instance type:
   * `t2.micro`
     
7. Create a new key pair:
   * Example: `linux-key.pem`
     
8. Configure network settings:
   * Enable SSH
   * Enable HTTP (optional)
     
9. Click **Launch Instance**

### Launching Windows VM

1. Click **Launch Instance**
2. Enter instance name: `Windows-VM`
3. Choose:
   * Windows Server AMI
     
4. Select instance type:
   * `t2.micro`
     
5. Create/use key pair
6. Enable RDP (Port 3389)
7. Launch instance

## Result

Successfully launched:

* Linux Virtual Machine
* Windows Virtual Machine
  using AWS EC2 service.

## Screenshots

### EC2 Dashboard - Instance
Shows both Linux and Windows instances in running state.

### Linux Instance Configuration
Shows Amazon Linux AMI selection and instance settings.

### Windows Instance Configuration
Shows Windows Server AMI selection and network configuration.

## Learning Outcome

- Learned how to launch EC2 virtual machines in AWS.
- Understood the difference between Linux and Windows instances.
- Learned basic cloud instance configuration and networking settings.
- Gained hands-on experience with AWS EC2 services.

## Note
Instances were stopped after the experiment to avoid unnecessary AWS usage charges.
