# DevOps Web Project

This project is a simple Java web application built and managed as part of my DevOps learning journey. It demonstrates how to use Git, GitHub, Maven, and AWS EC2 in a real-world workflow — including remote server development using VSCode and solving system-level issues like memory limitations.

---

## 🌐 Project Overview

The app consists of a basic JSP file served through a standard Java EE web structure. The code is hosted in a GitHub repository and pushed from an AWS EC2 instance via SSH and Git. The goal was to:
- Learn Git & GitHub fundamentals
- Practice Java web app structure with Maven
- Connect EC2 with GitHub via CLI
- Use VSCode's SSH Remote development
- Troubleshoot resource issues on low-RAM servers

---

## 🧾 File Structure

devops-web-project/
├── pom.xml
└── src/
└── main/
└── webapp/
├── index.jsp
└── WEB-INF/
└── web.xml

---

## 🧠 Technologies Used

- Java EE (JSP)
- Apache Maven
- AWS EC2 (Amazon Linux)
- Git & GitHub
- VSCode with Remote - SSH extension

---

## 🔄 Git Workflow

```bash
# Initialize Git
git init

# Add all files to staging
git add .

# Commit changes with a message
git commit -m "Updated index.jsp with new content"

# Push to GitHub
git push -u origin master

```
GitHub authentication uses a Personal Access Token (PAT) instead of a password.

---

⚙️ Build & Run
To build and deploy locally:

Clone the project

git clone https://github.com/JoseSnayers24/devops-web-project.git

Import into an IDE (e.g. IntelliJ, Eclipse) as a Maven project.

Deploy to a servlet container like Apache Tomcat.

Access via browser:

http://localhost:8080/devops-web-project/

Expected Output:

Hello World

This is my Devops web application working!
If you see this line on GitHub, it means your latest changes have been pushed to your cloud repository.

---

🛠 Challenges & Solutions

🔄 VSCode SSH Remote kept disconnecting

Problem:
When connecting to my EC2 instance via VSCode Remote - SSH, it kept crashing or getting stuck.

Cause:
My EC2 instance had only 1 GB of RAM, and VSCode’s remote extension caused the RAM to spike.

Solution:
I created a 2 GB swap file to add virtual memory, which stabilized the server.

# Create and enable 2 GB swap space

```
sudo fallocate -l 2G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile

```

# Make swap permanent
```
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```
After enabling swap, the connection became stable.

📚 What I Learned

Using Git from the terminal to manage code versions

Working with Maven project structure

Pushing to GitHub from an EC2 instance using PAT

Debugging server issues like memory limits

Connecting remote servers to VSCode for real-time development

---

## 🧭 What's Next?

This project is part of a growing DevOps journey. Here are the next milestones I plan to tackle:

- 🔐 **Secure Packages with CodeArtifact**  
  Manage and securely store your application’s dependencies.

- 🤖 **Continuous Integration with CodeBuild**  
  Automate builds and testing whenever you push changes to GitHub.

- 🚀 **Deploy a Web App with CodeDeploy**  
  Set up automated deployment pipelines to EC2 or other targets.

- 🏗️ **Infrastructure as Code with CloudFormation**  
  Define and manage infrastructure through code using templates.

Stay tuned as I build toward a fully automated CI/CD pipeline!

---

## 👨‍💻 Author

**Jose Snayers**  
[GitHub Profile](https://github.com/JoseSnayers24) 
[LinkedIn](https://www.linkedin.com/in/jose-snayers-6660b424b/)
