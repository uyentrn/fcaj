---
title: "Week 4 Worklog"
date: 2024-06-22
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* **Elastic Load Balancing (ELB):** Understand Application Load Balancer (ALB) Layer 7 & Network Load Balancer (NLB) Layer 4, Target Groups, and Health Checks.
* **Auto Scaling Group (ASG):** Master concepts of Launch Template, Auto Scaling Policies (Target Tracking, Step Scaling).
* **High Availability Architecture:** Combine ALB + ASG to build an automated server resource adjustment system based on actual demand.
* **Project:** Integrate SMTP email service, fully build APIs for the authentication flow (Request OTP, Register, Login, Refresh Token), and deploy security Middlewares (JWT Authentication, RBAC Authorization, Refresh Token Rotation).

### Tasks Implemented This Week:
| Day | Task | Start Date | Completion Date | Reference Materials |
| --- |----- | ---------- | --------------- | ------------------- |
| Mon | - Learn about Elastic Load Balancing: <br>&emsp; + ALB <br>&emsp; + NLB <br>&emsp; + GWLB <br> - Learn about Routing algorithms and Health Checks <br> - **Project:** <br>&emsp; + Integrate Email sending service via SMTP service <br>&emsp; + Build email helper to send verification codes and system notifications | 22/06/2026 | 22/06/2026 | [- Master All 3 AWS Load Balancers](https://www.youtube.com/watch?v=znQsN8KzF_o) <br> [- AWS Application Load Balancer - Routing Algorithms and Health Checking](https://www.youtube.com/watch?v=oRz4Ln1zOLg)|
| Tue | - Learn about Auto Scaling Group (ASG) <br> - Differentiate Launch Configuration and Launch Template <br> - **Project:** <br>&emsp; + Write API POST /api/auth/request-register-otp (send 6-digit OTP code to registered email) <br>&emsp; + Test successful OTP sending via SMTP | 23/06/2026 | 23/06/2026 | [Auto Scaling Groups](https://docs.aws.amazon.com/autoscaling/ec2/userguide/AutoScalingGroup.html) |
| Wed | - Learn about Dynamic Scaling policies: <br>&emsp; + Target Tracking <br>&emsp; + Dynamic Scaling Policy <br>&emsp; + Scheduled Scaling <br> - **Project:** <br>&emsp; + Write API POST /api/auth/register (register a new user account after OTP verification) <br>&emsp; + Deploy secure password hashing (Bcrypt/Argon2) | 24/06/2026 | 24/06/2026 | [Scaling Policies](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scale-based-on-demand.html) |
| Thu | - **Hands-on:** Create Application Load Balancer (ALB) routing traffic to 2 EC2 Web Servers running across 2 AZs <br> - **Project:** <br>&emsp; + Write API POST /api/auth/login (login, returning Access Token & Refresh Token) <br>&emsp; + Write API POST /api/auth/refresh (refresh Access Token) | 25/06/2026 | 25/06/2026 | [How to Create AWS Application Load Balancer(ALB)](https://www.youtube.com/watch?v=xJkWrEsT2Vs) |
| Fri | - **Hands-on:** <br>&emsp; + Create Launch Template from AMI, construct ASG (Min: 2, Desired: 2, Max: 4) attached to ALB <br>&emsp; + Configure auto scaling policy & test auto-scaling <br> - **Project:** <br>&emsp; + Build Middleware for JWT Check authentication and Refresh Token rotation <br>&emsp; + Deploy authorization Middleware (RBAC: Admin, Client) | 26/06/2026 | 26/06/2026 | [Auto Scaling Group (complete guide)](https://www.youtube.com/watch?v=ysIRuF7XQbk) |

### Week 4 Results Achieved:

* **Elastic Load Balancing (ELB) & High Availability:**
    * Clearly distinguished the features and use cases of Application Load Balancer (Layer 7), Network Load Balancer (Layer 4), and Gateway Load Balancer.
    * Mastered Routing algorithms and Health Check configuration to automatically route traffic safely to healthy instances.
    * Successfully practiced creating an ALB to balance and route traffic to 2 EC2 Web Servers located in 2 different Availability Zones (AZs).
* **Auto Scaling Group (ASG) & Auto-Scaling:**
    * Differentiated Launch Configuration and Launch Template; clearly understood flexible scaling policies (Target Tracking, Dynamic Scaling, Scheduled Scaling).
    * Successfully created a Launch Template from an AMI, initialized ASG (Min: 2, Desired: 2, Max: 4) directly attached to the ALB.
    * Successfully tested the auto-scaling capability of server resources under heavy load stress and the automated replacement mechanism for failed (Unhealthy) instances.
* **Backend Project Deployment (Auth Module):**
    * Successfully integrated SMTP service and built an automated email helper (OTP verification codes, system notifications).
    * Fully deployed the `POST /api/auth/request-register-otp` API (generate and send 6-digit OTP via email) with successful email delivery testing.
    * Fully deployed the `POST /api/auth/register` API (register account after OTP verification) integrating secure password hashing with Bcrypt/Argon2.
    * Fully deployed the `POST /api/auth/login` API (authenticate and issue Access Token & Refresh Token) and `POST /api/auth/refresh` API (refresh Access Token).
    * Successfully wrote and integrated JWT Check Middleware, Refresh Token rotation mechanism to prevent token theft/reuse, and role-based access control Middleware (RBAC: Admin, Client).