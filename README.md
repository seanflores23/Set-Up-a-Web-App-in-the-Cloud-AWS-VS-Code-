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

# Set permissions for the private key
chmod 400 nextwork-keypair.pem

```
### 3. SSH Into EC2 Instance
```
bash
Copy
Edit
ssh -i nextwork-keypair.pem ec2-user@[EC2_IPV4_ADDRESS]

```
### 4. Install Java & Maven on EC2
```
bash
Copy
Edit
# Update packages
sudo yum update -y

# Install Java
sudo amazon-linux-extras enable corretto8
sudo yum install java-1.8.0-amazon-corretto -y

# Install Maven
sudo yum install maven -y

```
### 5. Generate Web App Using Maven
```
bash
Copy
Edit
mvn archetype:generate
# Follow the interactive prompts to select the webapp template and name your project

```
🖥️ VS Code Remote SSH Setup
Install the Remote - SSH extension in VS Code.

Add a new SSH host in your ~/.ssh/config file:
```
bash
Copy
Edit
Host aws-webapp
  HostName [EC2_IPV4_ADDRESS]
  User ec2-user
  IdentityFile ~/Desktop/DevOps/nextwork-keypair.pem
```
In VS Code, open the Command Palette → “Remote-SSH: Connect to Host” → aws-webapp.

🛠️ Modify the Web App
Use VS Code’s file explorer to open your generated web app.

Edit the src/main/webapp/index.jsp file:
```
html
Copy
Edit
<html>
  <body>
    <h1>Hello, Sean!</h1>
    <p>This is my webapp working.</p>
  </body>
</html>
```
##📸 Sample Output
After deploying the app successfully, the browser displays:
Hello, Sean!
This is my webapp working.

##💡 Reflection
This project took me approximately 1 hour.
The most challenging part was setting up Maven and connecting EC2 to VS Code.
The most rewarding moment was seeing everything work end-to-end inside a cloud-based server environment.

##📚 Next Steps
🔧 Continue building more DevOps projects to complete a full CI/CD pipeline!
🧠 Learn how to deploy this app with Jenkins, GitHub Actions, or Docker in upcoming projects.

##🔗 Resources
AWS EC2 Docs
Maven Documentation
Remote - SSH for VS Code

##👤 Author
Sean Carlo G. Flores
NextWork Student @ nextwork.org
