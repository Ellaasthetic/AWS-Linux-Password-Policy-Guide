# Documentation Guide for Configuring Password Policies on an EC2 Linux AWS Instance
Welcome to the Cloud Security Lab Project to demonstrate the configuration of password policies on an EC2 Linux AWS Instance using a Windows PC.

This repository contains a step-by-step guide to configuring a secure password policy on a Linux instance hosted on AWS.

## Project Overview
Password policies define rules that enhance the strength and effectiveness of user authentication. They help protect systems from brute force attacks, unauthorized access, and insider threats by ensuring that only secure, non-trivial passwords are accepted.

In today's digital age, password security is a critical aspect of protecting sensitive information and systems. A well-defined password policy is essential for ensuring the security and integrity of Linux instances on AWS. This guide provides a comprehensive overview of configuring password policies on Linux AWS instances, highlighting best practices and step-by-step instructions for implementation.

## 🛠️ Tools & Technologies Used in This Guide
### 1. AWS EC2 Instance
- **Description:** Amazon Elastic Compute Cloud provides resizable compute capacity in the cloud. This gives us the Linux environment we need.
- **Purpose:** Hosts the Linux virtual machine where password policy configuration is demonstrated.

### 2. PuTTYgen
- **Description:** A key generator tool used to convert OpenSSH .pem files to PuTTY .ppk format.
- **Purpose:** Converts the AWS-provided `.pem` private key into `.ppk`, required by PuTTY on Windows.

### 3. PuTTY
- **Description:** A free and open-source terminal emulator for Windows that supports SSH.
- **Purpose:** Used to securely connect to the EC2 Linux instance from a Windows computer using the `.ppk` key.