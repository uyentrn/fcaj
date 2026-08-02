---
title: "Week 9 Worklog"
date: 2026-07-27
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:
* **Research Security Configuration Management & Continuous Integration/Continuous Deployment (CI/CD):** Master risks of exposing security credentials (Secrets/API Keys), practice managing environment variables securely with AWS Systems Manager (SSM) Parameter Store (SecureString, AWS SDK), learn CI/CD Pipeline workflow, and build automated Workflow for build/deploy upon Git push.
* **Complete Reviews Module & Summarize Internship Report:** Design Schema and deploy full set of CRUD APIs for Reviews Module, while reviewing all 9 weeks of Worklogs, aggregating technical documentation, and finalizing the internship report.

### Tasks Implemented This Week:
| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | ---- | ---------- | --------------- | ------------------- |
| Mon | - Research risks of hardcoding secrets (Secrets/API Keys) in source code <br> - Learn about AWS Systems Manager (SSM) Parameter Store service <br> - **Project:** Design Prisma Schema for Reviews Module (Review) and write APIs: <br>&emsp; + Write API POST /api/products/{id}/reviews (submit product review/rating for Client who purchased the item) <br>&emsp; + Write API GET /api/products/{id}/reviews (get all reviews for a product) | 27/07/2026 | 27/07/2026 | [AWS Parameter Store Overview](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html) |
| Tue | - **Hands-on:** <br>&emsp; + Store parameters (SecureString) on Parameter Store <br>&emsp; + Retrieve parameters directly from application/Lambda using AWS SDK <br> - **Project:** <br>&emsp; + Write API PUT /api/reviews/{id} (update created review for Client) <br>&emsp; + Write API DELETE /api/reviews/{id} (delete review by ID for Client) <br>&emsp; + Write API DELETE /api/admin/reviews/{id} (delete review by ID for Admin) | 28/07/2026 | 28/07/2026 | [Creating Secure and Encrypted String Parameters](https://www.youtube.com/watch?v=cBIAjH_Sy-A) |
| Wed | - Learn overall CI/CD Pipeline workflow (Build, Test, Deploy) in modern software projects | 29/07/2026 | 29/07/2026 | [The IDEAL & Practical CI / CD Pipeline](https://www.youtube.com/watch?v=OPwU3UWCxhw) |
| Thu | - **Hands-on:** <br>&emsp; + Set up automated Workflow with GitHub Actions (or AWS CodePipeline) to build <br>&emsp; + Deploy source code to S3/ AWS App Runner on every `git push` operation | 30/07/2026 | 31/07/2026 | [Building automated CI/CD using AWS CodePipeline, ECS, Fargate, CodeBuild, CodeDeploy, Github](https://www.youtube.com/watch?v=7L3vJlwOTnk) |
| Fri | - Review and finalize the internship report | 31/07/2026 | 31/07/2026 |  |

### Week 9 Results Achieved:
* **Configuration Management & Secrets Management:**
    * Deeply understood security risks associated with hardcoding secrets, passwords, or API Keys directly into source code.
    * Successfully operated AWS Systems Manager (SSM) Parameter Store to manage and store configurations and environment variables.
    * Practiced storing encrypted parameters (`SecureString`) and wrote code using AWS SDK to retrieve secrets safely from applications/Lambda.
* **Continuous Deployment Automation (CI/CD Pipeline):**
    * Mastered standard concepts and workflows of a CI/CD pipeline (Build, Test, Deploy) in modern software development.
    * Successfully built automated Workflows using GitHub Actions (or AWS CodePipeline), automatically triggering build and deployment processes to S3 / AWS App Runner upon executing `git push`.
* **Backend Project Deployment (Review Module) & Report Finalization:**
    * Completed Prisma Schema design for the Reviews Module (Review).
    * Deployed API set for Client: `POST /api/products/{id}/reviews` (submit product review/rating after purchase), `GET /api/products/{id}/reviews` (view product review list), `PUT /api/reviews/{id}` (edit review), and `DELETE /api/reviews/{id}` (delete own review).
    * Deployed API `DELETE /api/admin/reviews/{id}` for Admin to manage and moderate inappropriate review content.
    * Completed the entire internship dossier including summary report, project technical documentation, and full 9-week Worklog system.