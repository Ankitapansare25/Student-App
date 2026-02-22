
# 🎓 Student Management Application

A Java-based Student Management Web Application deployed on AWS EC2 using Apache Tomcat and automated with Jenkins CI/CD pipeline.

---

## 🚀 Project Overview

This project demonstrates:

- Java Web Application development
- Maven build automation
- WAR file packaging
- Deployment on Apache Tomcat
- AWS EC2 hosting
- Jenkins CI/CD automation
- SSH-based remote deployment

---

## 🛠️ Tech Stack

- Java
- Maven
- Apache Tomcat 10
- Jenkins
- AWS EC2
- GitHub
- SSH

---

## 🏗️ Infrastructure Details

- Application hosted on AWS EC2 (Ubuntu)
- Apache Tomcat installed on server
- Deployment path:

```
/var/lib/tomcat10/webapps
```

- Application deployed as:

```
ROOT.war
```

---

## 🔄 CI/CD Pipeline Workflow (Detailed Explanation)

### 1️⃣ Code Checkout
Jenkins pulls the latest source code from the GitHub main branch.

### 2️⃣ Build Application
Jenkins executes:

```
mvn clean package
```

This command:
- Cleans previous builds
- Compiles the Java application
- Generates a WAR file inside the `target/` folder

### 3️⃣ Deployment to EC2 Server

Jenkins performs the following steps:

- Identifies the generated WAR file
- Securely copies it to the EC2 server using SCP
- Connects to the server via SSH
- Removes old application files from Tomcat webapps directory
- Renames the new WAR file to `ROOT.war`
- Sets proper ownership to `tomcat:tomcat`
- Restarts the Tomcat service

### 4️⃣ Post Deployment

If deployment is successful, Jenkins displays:

```
App deployed! Visit: http://<SERVER_IP>:8080/
```

---

## 📂 Jenkins Pipeline Stages

- Checkout
- Build WAR
- Deploy to Tomcat
- Post Success/Failure Handling

---

## 🌐 Access Application

After successful deployment:

```
http://<EC2_PUBLIC_IP>:8080/
```

---

## 📌 DevOps Concepts Used

- Continuous Integration
- Continuous Deployment
- Remote Server Deployment using SSH
- WAR Packaging
- Service Management using systemctl
- Secure Credential Handling in Jenkins

---
## Author
Ankita pansare

---
