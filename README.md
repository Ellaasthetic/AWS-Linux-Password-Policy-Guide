# Documentation Guide for Configuring Password Policies on an EC2 Linux AWS Instance
Welcome to the Cloud Security Lab Project to demonstrate the configuration of password policies on an EC2 Linux AWS Instance using a Windows PC.

This repository contains a step-by-step guide to configuring a secure password policy on a Linux instance hosted on AWS.

## Project Overview
Password policies define rules that enhance the strength and effectiveness of user authentication. They help protect systems from brute force attacks, unauthorized access, and insider threats by ensuring that only secure, non-trivial passwords are accepted.

In today's digital age, password security is a critical aspect of protecting sensitive information and systems. A well-defined password policy is essential for ensuring the security and integrity of Linux instances on AWS. This guide provides a comprehensive overview of configuring password policies on Linux AWS instances, highlighting best practices and step-by-step instructions for implementation.

## ✅ Best Practices for Password Policies
Implementing effective password policies on Linux systems, especially those running on AWS is a foundational security control. These best practices help protect against unauthorized access, brute-force attacks, and credential compromise.

### 1. Enforce Strong Passwords
Require users to include uppercase and lowercase letters, numbers, and special characters in their passwords.

Simple passwords like password123 are vulnerable to brute-force and dictionary attacks. Requiring complexity significantly increases the time and computing power needed to crack a password.

### 2. Set Minimum Password Length
Enforce a minimum length of 12 characters or more.

A longer password dramatically increases the number of possible combinations, making it exponentially harder to crack. For example, an 8-character password can often be brute-forced in minutes, while a 12-character password could take years.

### 3. Implement Password Expiration
Require password changes every 60–90 days, depending on organizational policy.
Regular password changes limit the duration of exposure in case a password is compromised. It also encourages users to adopt a proactive security mindset.

### 4. Enforce Password History
Prevent users from reusing their last 5–10 passwords.
Without history enforcement, users often recycle the same few passwords. This defeats the purpose of periodic changes and increases the risk of credential reuse across systems.

### 5. Configure Account Lockout Thresholds
Lock accounts after 3–5 failed login attempts, with a cooldown or admin unlock required.
This helps mitigate brute-force attacks by limiting how often an attacker can attempt guesses. It also provides an early warning of potential intrusion attempts.

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