---
title: "Week 8 Worklog"
date: 2026-07-20
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Understand Containerization concepts with Docker in software development.
* Master application packaging, Dockerfile optimization, and pushing Docker Images to AWS ECR (Elastic Container Registry).
* Deploy Web applications from Containers to AWS using simple, automated AWS App Runner service.
* Configure Auto-deployment mechanisms and operational parameters (Environment Variables, Scaling, Health Check, Custom Domain) on AWS App Runner.
* Evaluate, summarize costs, and optimize testing resources on AWS.
* **Project:** Deploy a full set of Cart Management APIs, Checkout flow creating orders applying Database Transactions, automated email notification system for orders/status, and advanced Order Management APIs for Admin.


### Tasks Implemented This Week:
| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | ---- | ---------- | --------------- | ------------------- |
| Mon | - Learn Containerization concepts & Compare Docker with Virtual Machine (EC2) <br> - Write a simple `Dockerfile` to package a Web application (Node.js/Python/React) <br> - **Project:** <br>&emsp; + Write API GET /api/cart (get current user's cart for Client) <br>&emsp; + Write API POST /api/cart (add product to cart with variant_id, quantity for Client) | 20/07/2026 | 20/07/2026 | [Learn Docker & Deploy to AWS (Beginner Tutorial)](https://www.youtube.com/watch?v=1_AlV-FFxM8&t=575s) |
| Tue | - Learn about AWS ECR service (Docker Image Registry) <br> - **Hands-on:** Create Repository on ECR, use AWS CLI to log in and push Docker Image to ECR <br> - **Project:** <br>&emsp; + Write API PUT /api/cart/{itemId} (update item quantity in cart for Client) <br>&emsp; + Write API DELETE /api/cart/{itemId} (remove item from cart for Client) | 21/07/2026 | 21/07/2026 | [- Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html) <br> [- Push docker to Amazon ECR](https://www.youtube.com/watch?v=OaSxs2uqipQ) |
| Wed | - Learn about AWS App Runner service (Automated Container service for Software Developers without managing infrastructure) <br> - **Hands-on:** Configure App Runner to pull image from ECR and automatically deploy Web application to the internet <br> - **Project:** <br>&emsp; + Test Cart management flow on Postman <br>&emsp; + Handle edge cases (out of stock items, updating quantity exceeding inventory) | 22/07/2026 | 22/07/2026 | [- AWS App Runner](https://docs.aws.amazon.com/apprunner/latest/dg/what-is-apprunner.html) <br> [- Deploying Next.js on AWS App Runner](https://www.youtube.com/watch?v=XMIgCgkzhfk) |
| Thu | - **Project:** <br>&emsp; + Write API POST /api/orders (Checkout: convert cart to order for Client applying Database Transaction) <br>&emsp; + Write API POST /api/orders/checkout (create new order from current cart) + Integrate automatic trigger for sending pending order notification email to Client <br>&emsp; + Write API GET /api/admin/orders (view order history of all users for Admin) <br>&emsp; + Write API GET /api/admin/orders/:id (view details or specific order status for Admin) | 23/07/2026 | 23/07/2026 | |
| Fri | - Learn about Amazon CloudWatch Metrics, Dashboards <br> - Learn how to set up CloudWatch Alarms sending notifications via Amazon SNS <br> - **Project:** <br>&emsp; + Write API PATCH /api/admin/orders/{id} (update order status: paid, shipping, completed, cancelled) <br>&emsp; + Deploy automatic email notification for new status to customer when Admin updates | 24/07/2026 | 24/07/2026 | [- Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [- How To Create a CloudWatch Dashboard](https://www.youtube.com/watch?v=5QK3FB1EsV0) |


### Week 8 Results Achieved:
* **Containerization & AWS ECR:**
    * Thoroughly understood differences between Containerization (Docker) and Virtual Machines (EC2), mastering environment-independent application packaging thinking.
    * Successfully packaged Web application into standard Docker Image and optimized image size using Multi-stage build techniques.
    * Created ECR Repository, fluently used AWS CLI to authenticate, push, and manage Docker Image tagging securely on AWS ECR registry.
* **AWS App Runner & System Monitoring (CloudWatch):**
    * Mastered AWS App Runner knowledge - PaaS/Serverless Container solution helping deploy applications automatically without server infrastructure management.
    * Configured App Runner to pull images directly from ECR and successfully deployed Web application to the Internet along with setting up Auto-deploy mechanism upon new builds.
    * Mastered managing environment variables, setting up Health Checks, and controlling Cloud resource costs.
    * Explored Amazon CloudWatch Metrics, Dashboards configurations, and mechanisms for establishing CloudWatch Alarms to send automated alerts via Amazon SNS.
* **Backend Project Deployment (Cart & Order Modules):**
    * Deployed a complete set of Cart Management APIs for Client: `GET /api/cart` (get current cart), `POST /api/cart` (add product to cart with `variant_id` and `quantity`), `PUT /api/cart/{itemId}` (update quantity), and `DELETE /api/cart/{itemId}` (remove item from cart).
    * Thoroughly handled edge cases in cart management (out of stock items, updated quantity exceeding inventory) and comprehensively tested on Postman.
    * Deployed Checkout APIs `POST /api/orders` & `POST /api/orders/checkout` creating orders from current cart, applying **Database Transactions** to ensure data integrity (deducting inventory, clearing cart) and integrated automatic order confirmation email sending for Client.
    * Deployed Order Management APIs for Admin: `GET /api/admin/orders` (view list of all orders), `GET /api/admin/orders/{id}` (view order details), and `PATCH /api/admin/orders/{id}` (update order status: `paid`, `shipping`, `completed`, `cancelled`).
    * Integrated automated trigger sending order status update email notification to customer whenever Admin updates order status.