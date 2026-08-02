---
title: "Week 5 Worklog"
date: 2024-06-29
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* **Amazon RDS Relational Database:** Learn RDS (MySQL/PostgreSQL), Multi-AZ concepts (High Availability), and Read Replicas (Scalability).
* **Amazon DynamoDB NoSQL Database:** Understand Key-Value/Document architecture, Partition Key, Sort Key, Read/Write Capacity Units (RCU/WCU).
* **Database Deployment Practice:** Connect Web application on EC2 to RDS database placed in a separate Subnet.
* **Project:** Complete all remaining APIs of the Authentication Module (Logout, Forgot/Reset Password, User Profile), perform automated/independent testing, and design detailed database Schema for Product Management Module.

### Tasks Implemented This Week:
| Day | Task | Start Date | Completion Date | Reference Materials |
| --- |----- | ---------- | --------------- | ------------------- |
| Mon | - Learn about Amazon RDS and supported Database Engines <br>&emsp; + MySQL <br>&emsp; + PostgreDB <br> - Compare Multi-AZ Deployment synchronous replication mechanism with Read Replicas asynchronous mechanism <br> - **Project:** <br>&emsp; + Write API POST /api/auth/logout (logout/invalidate session) <br>&emsp; + Write API POST /api/auth/forgot-password (request OTP via email for password recovery) | 29/06/2026 | 29/06/2026 | [Amazon RDS Features](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html) |
| Tue | - Learn about Amazon DynamoDB (NoSQL) <br> - Analyze data structures: <br>&emsp; + Table <br>&emsp; + Item <br>&emsp; + Attribute <br> - Differentiate Partition Key (Simple Primary Key) and Composite Key (Partition Key + Sort Key) <br> - **Project:** <br>&emsp; + Write API POST /api/auth/reset-password (verify OTP, set new password, and log out of all devices) <br>&emsp; + Test password recovery flow | 30/06/2026 | 30/06/2026 | [- DynamoDB Developer Guide](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html) <br> [- DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html)|
| Wed | - Learn about DynamoDB Provisioned and On-Demand Capacity Mode <br> - Learn about Global Tables & DynamoDB Accelerator (DAX) <br> - **Project:** <br>&emsp; + Write API GET /api/me (get current user profile) <br>&emsp; + Write API PATCH /api/me (update current user profile) | 01/07/2026 | 01/07/2026 | [- DynamoDB on-demand and provisioned capacity](https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/capacity.html) <br> [- DAX & Global Table](https://www.youtube.com/watch?v=HZLQbj3Cpyo)|
| Thu | - **Hands-on:** <br>&emsp; + Create DB Subnet Group <br>&emsp; + Launch Multi-AZ RDS MySQL Instance in Private Subnet and connect from EC2 Web Server <br> - **Project:** <br>&emsp; + Write Unit Tests for Register/Login flows <br>&emsp; + Create Postman Collection and test the entire Authentication Module | 02/07/2026 | 02/07/2026 | [RDS Multi-AZ Tutorial](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateDBInstance.html) |
| Fri | - **Hands-on:** <br>&emsp; + Create a new DynamoDB Table on AWS Management Console with a specific Partition Key <br>&emsp; + Perform Create, Read, Update, Delete (CRUD) operations directly on the Console interface <br>&emsp; + Use `aws dynamodb put-item`, `aws dynamodb get-item`, `aws dynamodb scan` commands to manipulate data via CLI <br> - **Project:** Design DB Schema for: <br>&emsp; + Categories / Scent Families / Brands (Categories, Brands) <br>&emsp; + Products, Product Variants, and Scent Notes (Products, Product Variants, Attributes/Scent Notes) | 03/07/2026 | 03/07/2026 | [DynamoDB CLI Tutorial](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SampleData.html) |

### Week 5 Results Achieved:
* **Amazon RDS (Relational Database Service):**
    * Clearly distinguished the synchronous replication mechanism of Multi-AZ Deployment (ensuring High Availability and automatic Failover) and the asynchronous replication mechanism of Read Replicas (optimizing read performance and Scalability).
    * Successfully practiced creating DB Subnet Group and RDS MySQL Instance with Multi-AZ configuration placed entirely within Private Subnets, ensuring standard security without public Internet exposure.
    * Securely connected Web application on EC2 to RDS MySQL in a separate Subnet.
* **Amazon DynamoDB (NoSQL Database):**
    * Mastered core DynamoDB components (Table, Item, Attribute) and differentiated Partition Key (Simple Primary Key) from Composite Key (Partition Key + Sort Key).
    * Differentiated Provisioned Capacity Mode and On-Demand Capacity Mode; understood the operational principles of Global Tables (multi-region) and DynamoDB Accelerator - DAX (In-memory cache).
    * Successfully practiced creating a DynamoDB Table on AWS Console, performing CRUD operations directly on Console, and fluently using AWS CLI commands (`put-item`, `get-item`, `scan`).
* **Backend Project Deployment:**
    * Successfully wrote and integrated the `POST /api/auth/logout` API (invalidate session) and `POST /api/auth/forgot-password` API (request password reset OTP via email).
    * Successfully deployed the `POST /api/auth/reset-password` API (verify OTP, set new password, and automatically invalidate all login sessions across all devices).
    * Successfully deployed User Profile Management APIs: `GET /api/me` (get current user profile) and `PATCH /api/me` (update personal profile).
    * Wrote Unit Tests for Register/Login flows, established Postman Collection, and comprehensively tested all functional flows of the Authentication Module.
    * Completed detailed Prisma Schema design for Product Module: Categories/Brands/Scent Families (Categories, Brands), Products & Product Variants (Products, Product Variants), and Attributes/Scent Notes (Attributes/Scent Notes).