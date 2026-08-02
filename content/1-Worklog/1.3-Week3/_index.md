---
title: "Week 3 Worklog"
date: 2024-06-15
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* **Amazon S3 Object Storage:** Master S3 Buckets structure, Objects, and Storage Classes (Standard, IA, Glacier, Deep Archive).
* **Lifecycle Management & Versioning:** Use S3 Versioning, Object Lock, and set up S3 Lifecycle Rules to optimize costs.
* **Security & Static Web Hosting:** Configure Bucket Policies, CORS, SSE Encryption, and practice hosting static websites on S3.
* **Project:** Initialize repository, set up development environment with Docker, establish Prisma ORM (Schema Auth Module, Migration, Seed data), and build a standardized Express server framework.

### Tasks Implemented This Week:
| Day | Task | Start Date | Completion Date | Reference Materials |
| --- |----- | ---------- | --------------- | ------------------- |
| Mon | - Learn about Amazon S3 concepts: <br>&emsp; + Buckets <br>&emsp; + Keys <br>&emsp; + Metadata <br> - Differentiate S3 Storage Classes and cost models <br> - **Project:** <br>&emsp; + Create repository for Backend on GitHub <br>&emsp; + Build standard folder structure for the project | 15/06/2026 | 15/06/2026 | [- Amazon S3 Overview](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html) <br> [- Simple Storage Service (S3)](https://youtu.be/p9ddQvOoNQ4?si=Bpba8jaDgXIEXEfP)|
| Tue | - Learn about S3 Versioning & S3 Object Lock <br> - Configure S3 Lifecycle Rules to automatically transition storage tiers <br> - **Project:** <br>&emsp; + Initialize Dockerfile and docker-compose.yml for PostgreSQL and Node.js <br>&emsp; + Initialize Prisma ORM and configure environment variables .env (DATABASE_URL, PORT, JWT_SECRET, SMTP) | 16/06/2026 | 16/06/2026 | [S3 Lifecycle Management](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html) |
| Wed | - Learn about S3 security mechanisms: <br>&emsp; + Bucket Policy <br>&emsp; + IAM Policy <br> - S3 encryption methods: <br>&emsp; + SSE-S3 <br>&emsp; + SSE-KMS <br> - **Project:** <br>&emsp; + Design overall Prisma Schema for Auth Module (User, Role, RefreshToken, PasswordResetOTP) <br>&emsp; + Write Migration script to initialize the initial database | 17/06/2026 | 17/06/2026 | [S3 Security & Policies](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-management.html) |
| Thu | - **Hands-on:** <br>&emsp; + Package Web application (HTML/CSS/JS) <br>&emsp; + Configure S3 Static Website Hosting with Bucket Policy allowing Public Read <br> - **Project:** <br>&emsp; + Write seed.js script using Prisma Client to create sample data (Roles: Admin, Client and default Admin account) <br>&emsp; + Test seeding data into Docker PostgreSQL via npx prisma db seed command | 18/06/2026 | 18/06/2026 | [Enable static website feature](https://000057.awsstudygroup.com/vi/3-staticwebsite/) |
| Fri | - Learn about S3 Cross-Region Replication (CRR) <br> - **Project:** <br>&emsp; + Initialize Express server, configure centralized error handling Middleware <br>&emsp; + Standardize Response structure (Success status: success, Error status: error) | 19/06/2026 | 19/06/2026 | [S3 Replication Guide](https://000057.awsstudygroup.com/vi/10-s3ccr/) |

### Week 3 Results Achieved:

* **S3 Data Management & Cost Optimization:**
    * Clearly understood the structure of Buckets, Keys, Metadata, and characteristics of each storage class (Standard, IA, Glacier, Deep Archive).
    * Mastered S3 Versioning, S3 Object Lock mechanisms, and successfully established S3 Lifecycle Rules to automatically transition storage tiers for cost optimization.
    * Explored operational principles of S3 Cross-Region Replication (CRR).
* **Security & S3 Hosting Practice:**
    * Successfully wrote Bucket Policy to tightly control access permissions, clearly understanding the difference between IAM Policy and Bucket Policy.
    * Differentiated and applied SSE-S3 and SSE-KMS data encryption methods.
    * Packaged static web application (HTML/CSS/JS) and successfully deployed to S3 Static Website Hosting with Public Read Policy configuration.
* **Backend Project Deployment:**
    * Initialized GitHub repository and set up a standard directory structure for the project.
    * Containerized and successfully ran PostgreSQL and Node.js environments via `Dockerfile` and `docker-compose.yml`.
    * Configured Prisma ORM, completed Prisma Schema design for Auth Module (User, Role, RefreshToken, PasswordResetOTP).
    * Successfully ran Migration script to initialize database and seed sample data (Roles, default Admin account) into PostgreSQL via `seed.js`.
    * Initialized Express server, installed centralized error handling Middleware system, and standardized API Response structure (`success` / `error`).