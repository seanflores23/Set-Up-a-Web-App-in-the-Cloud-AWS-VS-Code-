# Set-Up-a-Web-App-in-the-Cloud-AWS-VS-Code-
This project sets the foundation for a CI/CD pipeline by deploying a basic Java web application in the cloud using AWS EC2, SSH, and Maven—all through a remote development setup via Visual Studio Code (VS Code).
# ☁️ Set Up a Web App in the Cloud (AWS + VS Code)

This project sets the foundation for a CI/CD pipeline by deploying a basic Java web application in the cloud using AWS EC2, SSH, and Maven—all through a remote development setup via Visual Studio Code (VS Code).

---

## 🚀 Project Overview

This project is part one of a series of DevOps projects where I'm building a CI/CD pipeline! I launched an EC2 instance and connected to it via VS Code to generate and run a Java-based web application using Maven.

**Services I used:**  
- AWS EC2  
- SSH  
- VS Code  
- Maven  
- Java

**Key concepts I learned:**  
- Cloud server setup with AWS EC2  
- Remote development with SSH and VS Code  
- Java web app creation using Maven  
- Secure key management  
- Importance of IDEs for code efficiency

---

## 🧰 Prerequisites

Before starting, ensure you have:
- An AWS account
- [VS Code](https://code.visualstudio.com/) installed
- Remote - SSH extension in VS Code
- Java installed on the EC2 instance
- Maven installed on the EC2 instance

---

## ⚙️ Step-by-Step Setup

### 1. **Launch an EC2 Instance**
- Choose an Amazon Linux 2 AMI.
- Select a t2.micro instance (Free Tier eligible).
- Configure security group to allow only SSH (port 22).
- Create a key pair (e.g., `nextwork-keypair.pem`) and download it.

### 2. **Prepare Your Local Machine**
```bash
# Navigate to key file location
cd ~/Desktop/DevOps

# Set permissions for the private key
chmod 400 nextwork-keypair.pem
