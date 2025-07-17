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

ssh -i nextwork-keypair.pem ec2-user@[EC2_IPV4_ADDRESS]

# Update packages
sudo yum update -y

# Install Java
sudo amazon-linux-extras enable corretto8
sudo yum install java-1.8.0-amazon-corretto -y

# Install Maven
sudo yum install maven -y

mvn archetype:generate
# Follow the interactive prompts to select the webapp template and name your project

<html>
  <body>
    <h1>Hello, Sean!</h1>
    <p>This is my webapp working.</p>
  </body>
</html>

cd ~/Desktop/DevOps

💡 Reflection
This project took me approximately 1 hour.
The most challenging part was setting up Maven and connecting EC2 to VS Code.
The most rewarding moment was seeing everything work end-to-end inside a cloud-based server environment.

📚 Next Steps
🔧 Continue building more DevOps projects to complete a full CI/CD pipeline!
🧠 Learn how to deploy this app with Jenkins, GitHub Actions, or Docker in upcoming projects.

🔗 Resources
AWS EC2 Docs

Maven Documentation

Remote - SSH for VS Code

👤 Author
Sean Carlo G. Flores
NextWork Student @ nextwork.org


---

Let me know if you’d like a downloadable `README.md` file or if you want to add images (screenshots, diagrams), GitHub badges, or a deployment link.


# Set permissions for the private key
chmod 400 nextwork-keypair.pem
