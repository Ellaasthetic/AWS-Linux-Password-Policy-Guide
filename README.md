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


# 🛡️ Step-by-Step Guide: Implementing Password Policy on a Linux AWS Instance
This guide provides a detailed walkthrough on how to set up a Linux EC2 instance on AWS and implement password policy configurations for better system security.

## ✅ Step 1: Launch a Linux EC2 Instance
- Go to [AWS Console](https://aws.amazon.com/console/) and sign in as the **root user** or create an account.
- In the AWS Management Console:
   * Search for **"EC2"** and click to open the EC2 dashboard.
   * Click on **"Launch an Instance"**.
- Configure the instance:
   * **Name**: `Linux-Password-Policy` (example used in this demonstration)
   * **AMI**: Select `Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type`
   * **Instance Type**: Choose `t3.micro` (default eligible for Free Tier)
- Under **Key pair (login)**:
   * Click **"Create a new key pair"**
   * **Name**: `PolicyKey` (example used in this demonstration)
   * **Key pair type**: `RSA`
   * **Private key format**: `.pem`
   * Click **"Create key pair"** to download the `.pem` file.
- **Network settings**: Leave as default.
- **Storage**: Use default — 1 x 8 GiB `gp2`
- Click **"Launch Instance"**

## 🔗 Step 2: Connect to the Instance
### Get the Public IP
* In your EC2 dashboard, go to **Instances**
* Copy your instance’s **Public IPv4 address**

### Install PuTTY (if not installed)
* Download [PuTTY Installer](https://www.putty.org/)
* It includes **PuTTY** and **PuTTYgen**

### Convert `.pem` to `.ppk` using PuTTYgen
   - Open your file explorer > Downloads
   - open the `.pem` key file you downloaded using PuTTYgen (PuTTYgen comes with PuTTY when you install it)
   - click on save private key, and exit.

   * Confirm saving without a passphrase
This generates a `.ppk` file you’ll use to authenticate with PuTTY

### Connect with PuTTY
- Open **PuTTY**
- Under **Session**:
    * In **Host Name (or IP address)**, paste your **Public IPv4**
- In the left panel, expand:
     * `Connection` → `SSH` → `Auth`
     * Under **"Private key file for authentication"**, click **Browse** and select your `.ppk` file
- Click **Open** to start the session
   * click on open and select connect once when prompted with security alert
- Login as:
   ```bash
   ec2-user
   ```
