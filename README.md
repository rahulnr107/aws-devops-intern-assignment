# AWS DevOps Engineer Intern Assignment

## Objective

Deploy a simple static website on an AWS EC2 Ubuntu instance using Nginx and document the complete deployment process.

---

# Technologies Used

* Amazon EC2
* Ubuntu 24.04 LTS
* Nginx
* Linux
* Git
* GitHub
* SSH

---

# Project Structure

```
.
├── index.html
└── README.md
```

---

# Task 1: AWS EC2 Setup

## Step 1: Launch EC2 Instance

* Logged in to the AWS Management Console.
* Opened the EC2 Dashboard.
* Clicked **Launch Instance**.
* Configured the instance with the following settings:

  * **Name:** AWS-DevOps-Assignment
  * **AMI:** Ubuntu Server 24.04 LTS
  * **Instance Type:** t2.micro (Free Tier)

---

## Step 2: Create a Key Pair

Created a new key pair in `.pem` format and downloaded it for SSH authentication.

Example:

```
assignment-key.pem
```

---

## Step 3: Configure Security Group

Created a Security Group with the following inbound rules:

| Type | Port | Source               |
| ---- | ---- | -------------------- |
| SSH  | 22   | My IP                |
| HTTP | 80   | Anywhere (0.0.0.0/0) |

---

## Step 4: Launch the Instance

Launched the EC2 instance and waited until its status changed to **Running**.

---

## Step 5: Connect to EC2 via SSH

Used the following command to connect to the instance:

```bash
ssh -i assignment-key.pem ubuntu@<EC2_PUBLIC_IP>
```

Example:

```bash
ssh -i assignment-key.pem ubuntu@54.xxx.xxx.xxx
```

---

# Task 2: Linux Basics & Nginx Installation

## Update Package Repository

```bash
sudo apt update
```

## Upgrade Installed Packages

```bash
sudo apt upgrade -y
```

## Install Nginx

```bash
sudo apt install nginx -y
```

## Check Nginx Status

```bash
sudo systemctl status nginx
```

Expected output:

```
Active: active (running)
```

## Restart Nginx

```bash
sudo systemctl restart nginx
```

---

# Linux Commands Used

## Check Disk Usage

```bash
df -h
```

## Check Memory Usage

```bash
free -h
```

## View Running Processes

```bash
ps aux
```

or

```bash
top
```

---

# Task 3: Deploy the Website

Navigate to the Nginx web root:

```bash
cd /var/www/html
```

Remove the default Nginx page:

```bash
sudo rm index.nginx-debian.html
```

Create a new HTML file:

```bash
sudo nano index.html
```

Paste the HTML content into the file and save it.

Restart the Nginx service:

```bash
sudo systemctl restart nginx
```

Open the website in a browser:

```
http://<EC2_PUBLIC_IP>
```

The custom webpage is now accessible from the internet.

---

# Git Commands Used

Initialize Git repository:

```bash
git init
```

Add files:

```bash
git add .
```

Commit changes:

```bash
git commit -m "Initial commit"
```

Add remote repository:

```bash
git remote add origin https://github.com/<username>/<repository-name>.git
```

Rename the default branch:

```bash
git branch -M main
```

Push the project to GitHub:

```bash
git push -u origin main
```

---

# Commands Summary

```bash
sudo apt update
sudo apt upgrade -y
sudo apt install nginx -y
sudo systemctl status nginx
sudo systemctl restart nginx
df -h
free -h
ps aux
cd /var/www/html
sudo rm index.nginx-debian.html
sudo nano index.html
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <repository-url>
git push -u origin main
```

---

# Outcome

* Successfully launched an Ubuntu EC2 instance.
* Configured Security Group for SSH and HTTP access.
* Connected securely using SSH.
* Installed and managed the Nginx web server.
* Hosted a custom HTML webpage on the EC2 instance.
* Uploaded the project files to GitHub with proper documentation.

---

# Learning Outcomes

* AWS EC2 instance creation and configuration.
* Security Group configuration.
* SSH authentication using a key pair.
* Basic Linux administration.
* Installing and managing Nginx.
* Hosting static websites.
* Using Git and GitHub for version control.

---

# Author

**Rahul N R**

AWS DevOps Engineer Intern Assignment
