# 🚀 CI/CD Pipeline for Static Website Deployment (AWS + GitHub)

![GitHub](https://img.shields.io/badge/GitHub-Source%20Code-blue?logo=github)
![AWS CodePipeline](https://img.shields.io/badge/AWS-CodePipeline-orange?logo=amazonaws)
![Amazon S3](https://img.shields.io/badge/Amazon-S3-green?logo=amazonaws)
![CloudFront](https://img.shields.io/badge/AWS-CloudFront-yellow?logo=amazonaws)
![CI/CD](https://img.shields.io/badge/CI%2FCD-Automated%20Pipeline-success)

This project demonstrates how to build a fully automated CI/CD pipeline using **AWS CodePipeline** to deploy a static website from **GitHub** to **Amazon S3**, with an added **manual approval gate** and **CloudFront distribution** for production-ready delivery.

---

## 🎯 Problem Statement
Developers should not have to manually deploy every website change.  
With this pipeline, every GitHub commit becomes a controlled, automated deployment.

---

## 🧰 Technologies Used
- **GitHub** – Source code repository  
- **AWS CodePipeline** – CI/CD orchestration  
- **Amazon S3** – Static website hosting  
- **Manual Approval Stage (CodePipeline)** – Deployment safety gate  
- **Amazon SNS** – Email notifications for approvals  
- **Amazon CloudFront** – Global CDN for high-performance web delivery  
- **HTML/CSS** – Static site content  

---

## 📌 Architecture Overview

```text
GitHub Repo
     │
     ▼
AWS CodePipeline (Source)
     │
     ▼
Manual Approval Stage (SNS Email)
     │
     ▼
S3 Static Website Bucket
     │
     ▼
Amazon CloudFront CDN
     │
     ▼
End Users
```


---

## ✅ Project Features
- ✅ Automatic deployment on every GitHub push  
- ✅ Manual approval step before production deployment  
- ✅ Email notifications for approval requests  
- ✅ Static website hosted on Amazon S3  
- ✅ CloudFront distribution for low latency and global access  
- ✅ No build stage required (pure static site deployment)  

---

## 🔁 CI/CD Workflow
1. Developer pushes code to the GitHub repository  
2. CodePipeline automatically detects the change  
3. Pipeline pauses at the Manual Approval stage  
4. Senior developer receives an approval email via SNS  
5. Once approved, the site is deployed to the S3 website bucket  
6. CloudFront updates and delivers the latest version to users  

---

## 🚀 Deployment Instructions

This project is not hosted live to avoid ongoing AWS costs.  
You can deploy the pipeline temporarily in your own AWS account to test it end-to-end.

### 🔧 Prerequisites
- AWS account with permissions for S3, CodePipeline, CloudFront, and SNS  
- GitHub repository containing your static website files (e.g., `index.html`)  
- AWS CLI or access to the AWS Management Console  

### 📦 Setup Steps
1. **Create an S3 bucket**
   - Enable static website hosting.
   - Upload a simple `index.html` file.

2. **Configure AWS CodePipeline**
   - Choose GitHub as the source provider.
   - Connect your repository and branch.

3. **Add a Manual Approval stage**
   - Use Amazon SNS to send approval requests via email.
   - Subscribe the approver’s email to the SNS topic.

4. **Deploy to S3**
   - After approval, CodePipeline copies files to the S3 bucket.

5. **Set up CloudFront**
   - Create a distribution pointing to your S3 bucket.
   - Use the CloudFront domain for production-ready delivery.

6. **Test the pipeline**
   - Push a change to GitHub.
   - Confirm CodePipeline detects the commit, pauses for approval, and deploys after approval.
   - Verify the update via the CloudFront URL.

### 💰 Cost Optimization
- Delete the S3 bucket and CloudFront distribution after testing to avoid charges.
- You can re-deploy anytime by repeating the setup steps.


---

## 🧪 Pipeline Testing Summary

To validate the pipeline during development:

1. A wording change was made to `index.html`.
2. The change was committed and pushed to GitHub.
3. CodePipeline automatically detected the update.
4. The pipeline paused at the Manual Approval stage.
5. An approval email was sent via SNS and approved by a senior developer.
6. The updated site was deployed to the S3 bucket.
7. CloudFront delivered the latest version to users.

✅ End-to-end automation confirmed working during testing.  
⚠️ Note: The demo website has been decommissioned to avoid AWS costs.

 

---

## ⚠️ Why Manual Approval Matters
Without approval gates:
- Untested changes can go directly to production  
- A single typo can take down a live website  
- Risk increases with team size  

The manual approval stage ensures **production safety and accountability**.  

---

## 📂 Repository Structure
```text
/
├── website.html
└── README.md
```


---

## 🧠 What This Project Demonstrates
- Real-world DevOps workflow automation  
- CI/CD pipeline governance using approvals  
- Secure and scalable static website hosting  
- AWS service integration across multiple layers  
- Production-ready deployment design  

