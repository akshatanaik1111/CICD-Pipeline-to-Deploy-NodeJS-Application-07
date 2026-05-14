# CI/CD Pipeline to Deploy Node.js Application-07

## 📌 Project Overview

This project demonstrates how to automate deployment of a Node.js application using AWS CI/CD services such as CodePipeline, CodeBuild, EC2, and Amazon S3.

The main objective of this project is to automatically build, test, and deploy the application whenever code changes are made. The pipeline improves deployment speed, reduces manual work, and ensures continuous integration and continuous deployment.

This project helps in understanding AWS DevOps workflow and cloud-based automation.

---

# 🎯 Objective

* Automate application deployment
* Implement Continuous Integration
* Implement Continuous Deployment
* Reduce manual deployment tasks
* Improve deployment efficiency
* Build DevOps automation workflow

---

# 🧰 AWS Services Used

## 1. AWS CodePipeline

Used to automate the CI/CD workflow.

## 2. AWS CodeBuild

Used to build and test the Node.js application.

## 3. Amazon EC2

Used to host the deployed Node.js application.

## 4. Amazon S3

Used to store deployment artifacts.

## 5. IAM Roles

Used to securely manage AWS permissions.

## 6. Security Groups

Used to securely manage inbound and outbound traffic.

---

# 🏗️ Project Architecture

The project architecture includes:

1. Uploading Source Code
2. Creating S3 Artifact Bucket
3. Creating CodeBuild Project
4. Creating CodePipeline Workflow
5. Connecting Build and Deploy Stages
6. Deploying Application to EC2
7. Automating Deployment Process
8. Testing CI/CD Pipeline

---

# ⚙️ Project Folder Structure

```bash
7. CICD Pipeline to Deploy Node.js Application/
│
├── app/
│   ├── package.json
│   ├── server.js
│   ├── index.js
│   └── public/
│
├── pipeline/
│   ├── buildspec.yml
│   ├── appspec.yml
│   └── deploy.sh
│
├── scripts/
│   ├── install_dependencies.sh
│   └── start_server.sh
│
├── images/
│
└── README.md
```

---

# ⚙️ Step-by-Step Implementation

## Step 1: Launch EC2 Instance

* Open AWS Console
* Go to EC2 Dashboard
* Launch EC2 Instance
* Select Ubuntu or Amazon Linux AMI
* Configure Security Group
* Allow:

  * HTTP (Port 80)
  * SSH (Port 22)

---

## Step 2: Install Node.js on EC2

Connect EC2 using SSH:

```bash
ssh -i key.pem ec2-user@your-public-ip
```

Install Node.js:

```bash
sudo yum update -y
curl -fsSL https://rpm.nodesource.com/setup_18.x | sudo bash -
sudo yum install -y nodejs
```

---

## Step 3: Create S3 Bucket

* Create Amazon S3 bucket
* Store deployment artifacts
* Configure bucket permissions

---

## Step 4: Create CodeBuild Project

* Configure build environment
* Connect source repository
* Add buildspec.yml file
* Configure build commands

Example buildspec.yml:

```yaml
version: 0.2

phases:
  install:
    commands:
      - npm install

  build:
    commands:
      - echo Build started
      - npm run build

artifacts:
  files:
    - '**/*'
```

---

## Step 5: Create CodePipeline

* Configure source stage
* Configure build stage
* Configure deployment stage
* Connect CodeBuild and EC2 deployment

---

## Step 6: Deploy Application

Run application:

```bash
npm install
node server.js
```

Verify deployment using browser.

---

## Step 7: Test CI/CD Pipeline

* Push code changes
* Trigger pipeline automatically
* Verify build success
* Verify automatic deployment

---

# 📸 Project Screenshots

## 🔹 S3 Bucket Creation

<img width="1894" height="760" alt="Screenshot 2026-04-23 205650" src="https://github.com/user-attachments/assets/e70b8a24-1db2-4638-bf22-c75ee52d9873" />

---

## 🔹 Application Deployment

<img width="1894" height="806" alt="Screenshot 2026-04-23 205440" src="https://github.com/user-attachments/assets/33f6ad97-5f11-461f-a693-986f813f8804" />

---
# ✅ Features

* Automated CI/CD Workflow
* Continuous Integration
* Continuous Deployment
* Automatic Build Trigger
* Automated Application Deployment
* Scalable Deployment Process
* AWS DevOps Automation

---

# 📚 Learning Outcomes

Through this project, I learned:

* How CI/CD pipelines work
* How AWS CodePipeline automates deployment
* How CodeBuild builds Node.js applications
* How to deploy applications on EC2
* Artifact storage using S3
* DevOps automation workflow
* AWS service integration

---

# 🚀 Future Improvements

* Add Docker Containerization
* Add HTTPS Support
* Configure Auto Scaling
* Add CloudWatch Monitoring
* Implement Blue-Green Deployment
* Add Notification System using SNS

---

# 🏁 Conclusion

This project successfully demonstrates CI/CD pipeline automation for deploying a Node.js application using AWS CodePipeline, CodeBuild, EC2, and S3. The infrastructure automates build and deployment workflows, reducing manual work and improving software delivery efficiency.

---

# 👩‍💻 Author

Akshata Naik

---
