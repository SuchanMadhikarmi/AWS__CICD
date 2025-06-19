# AWS CI/CD Pipeline Deployment Project

## Project Description

This project demonstrates the **CI/CD-based deployment** of an application on AWS using **Elastic Beanstalk, Amazon RDS, Bitbucket, S3, CodeBuild, and CodePipeline**. It automates the application deployment workflow, ensuring **scalability, security, and efficiency**.  

All screenshots of the deployment steps are available in the **`screenshots`** folder.

---

## Application Overview

This deployment pipeline is designed to manage and automate software releases using AWS services and Bitbucket integration.

### Architecture Overview:
- **Frontend:** Elastic Beanstalk (Tomcat-based environment)  
- **Backend Services:**  
  - **Amazon RDS (MySQL)** – Database  
  - **Bitbucket** – Source control repository  
  - **Amazon S3** – Artifact storage  
- **CI/CD Pipeline Components:**  
  - **AWS CodeBuild** – Automated testing and build  
  - **AWS CodePipeline** – Deployment automation  

---

## Repository Contents

| File | Description |
|------|-------------|
| `application.properties` | Configuration file for DB settings |
| `dbbackup/` | SQL scripts for database initialization |
| `buildspec.yml` | Build automation commands for CodeBuild |

---

## Deployment Flow

### Step 1: Elastic Beanstalk Setup
- Created an **Elastic Beanstalk environment** for hosting the application.
- Configured security settings, **environment variables**, and platform configurations.

### Step 2: RDS Database Configuration
- Created an **Amazon RDS (MySQL) instance** for backend storage.
- Configured **security group rules** to allow traffic **only from the Beanstalk instance**.

### Step 3: Database Initialization
- Installed **MySQL client** on the Beanstalk instance.
- Downloaded the **database backup** using `wget` from GitHub.
- Initialized the database using the SQL dump file.

### Step 4: Bitbucket Repository Setup
- Created a **Bitbucket repository** for version control.
- Generated **SSH key pair** and added the public key to Bitbucket.
- Cloned the existing **GitHub repository**, removed the origin, and pushed to **Bitbucket**.

### Step 5: Amazon S3 for Artifact Storage
- Created an **S3 bucket** to store application artifacts.
- Configured **permissions** for integration with AWS CodeBuild.

### Step 6: AWS CodeBuild Configuration
- Established a **connection between Bitbucket and CodeBuild**.
- Configured **buildspec.yml** to automate the build process.
- Initiated a **test build** to validate functionality.

### Step 7: AWS CodePipeline Setup
- Created a **custom pipeline** to automate deployment.
- Configured **Beanstalk role permissions** for access to CodeBuild and CodePipeline.
- Defined pipeline stages for **source retrieval, build, and deployment**.

### Step 8: Testing & Final Verification
- Executed the **CI/CD pipeline** to confirm successful integration.
- Verified that the application was **deployed successfully** in Beanstalk.
- Tested database connectivity and overall application workflow.

---

## Technologies Used

- **AWS Services:** Elastic Beanstalk, RDS, S3, CodeBuild, CodePipeline  
- **Version Control:** Bitbucket and GitHub  
- **Database Management:** MySQL with RDS  
- **Automation Tools:** Shell scripting, BuildSpec commands  

### Screenshots
Screenshots of all deployment steps are available in the **`screenshots`** folder.
