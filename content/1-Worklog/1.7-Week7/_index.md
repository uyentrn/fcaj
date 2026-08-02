---
title: "Week 7 Worklog"
date: 2024-07-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* **Content Delivery Network (Amazon CloudFront - CDN):** Master Edge Locations network architecture, Caching mechanism, Origin Access Control (OAC), Invalidation, and HTTPS/SSL security methods with AWS Certificate Manager (ACM).
* **Integrating CDN with AWS Infrastructure:** Deploy CloudFront as an acceleration & security layer sitting in front of S3 Bucket (Static Web/Assets) and Application Load Balancer / API Gateway (Dynamic Traffic).
* **Architecture Design & Representation:** Master using the official AWS icon set (AWS Architecture Icons v2024/2025), boundary drawing rules (Region, AZ, VPC, Subnet), and design a complete architecture diagram for a basic project using CDN.
* **Project:** Complete detailed viewing, deletion, pagination, multi-criteria filtering, product search APIs, and design database Schema for Cart and Order Modules.

### Tasks Implemented This Week:
| Day | Task | Start Date | Completion Date | Reference Materials |
| --- |----- | ---------- | --------------- | ------------------- |
| Mon | - Learn about Amazon CloudFront (CDN), the role of Edge Locations/Edge Caching in reducing latency <br> - Analyze CloudFront Distribution structure: Origin (S3, ALB, Custom Origin) & Behavior <br> - **Project:** <br>&emsp; + Write API GET /api/products (get product list supporting limit, offset pagination) <br>&emsp; + Build filter for products by query params: category, brand, scent, min_price | 13/07/2026 | 13/07/2026 | [Amazon CloudFront Developer Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| Tue | - Learn about Origin Access Control (OAC) security mechanism preventing direct user access to S3 <br> - Learn about Caching Policies, TTL (Time-To-Live), and CloudFront Invalidation technique (manual cache deletion) <br> - **Project:** <br>&emsp; + Write API GET /api/products/{id} (get detailed information of a perfume type including scent notes) <br>&emsp; + Write API DELETE /api/products/{id} (delete a product for Admin) | 14/07/2026 | 14/07/2026 | [- OAC](https://www.youtube.com/watch?v=KtWFGnB_dOs) <br> [- CloudFront Caching & Security](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Expiration.html) |
| Wed | - Learn about SSL/TLS encryption method via AWS Certificate Manager (ACM) and security integration against DDoS attacks (AWS WAF & Shield) <br> - **Project:** <br>&emsp; + Write API GET /api/search (search products by name with query string ?q=name) <br>&emsp; + Optimize product list query performance in Prisma | 15/07/2026 | 15/07/2026 | [- AWS Certificate Manager Tutorial](https://www.youtube.com/watch?v=dGciSbEfx3k) <br> [- AWS WAF](https://www.youtube.com/watch?v=u6lQo0SIJMc) |
| Thu | - **Hands-on:** <br>&emsp; + Test website on S3, create CloudFront distribution, configure HTTPS redirect, caching, error page <br>&emsp; + Set up Origin Access Control to block direct access to S3 bucket <br> - **Project:** <br>&emsp; + Fully test endpoints belonging to Product Management Module on Postman <br>&emsp; + Write test cases for product search filters and pagination | 16/07/2026 | 16/07/2026 | [Host a static website combining CloudFront and S3](https://www.youtube.com/watch?v=9X2IXN64ZLY) |
| Fri | - Learn how to draw a standard AWS architecture: <br>&emsp; + Data flows <br>&emsp; + AWS Global/ Region/ Edge Location/ VPC/ Subnet boundaries <br> - Use Draw.io / Lucidchart with the official **AWS Architecture Icons** set <br> - **Hands-on:** Draw a standard system architecture including *"User -> CloudFront (Edge Location) -> Route 53 -> ALB (Public Subnet) -> EC2 Auto Scaling (Private Subnet) + S3 (Static Content)"* <br> - **Project:** Design DB Schema for: <br>&emsp; + Shopping Cart (Cart, CartItem) <br>&emsp; + Orders (Order, OrderItem) | 17/07/2026 | 17/07/2026 | [- AWS Architecture Icons](https://aws.amazon.com/architecture/icons/) <br> [- Guide to drawing AWS architecture on draw.io](https://www.youtube.com/watch?v=l8isyDe-GwY&t=2091s) |

### Week 7 Results Achieved:

* **CloudFront Distribution Network (CDN) & Security:**
    * Thoroughly understood the role of Edge Locations/Edge Caching in reducing global latency and offloading origin resources.
    * Clearly understood CloudFront Distribution structure, distinguished Origin types (S3, ALB, Custom Origin), and configured separate Cache Behaviors for static and dynamic content.
    * Mastered Caching Policies, TTL (Time-To-Live), and CloudFront Invalidation techniques to manually purge cache upon content updates.
    * Deeply understood HTTPS/SSL encryption via AWS Certificate Manager (ACM) as well as DDoS attack mitigation solutions (AWS WAF & Shield).
    * Successfully practiced creating CloudFront Distribution for a static website on S3, configured HTTPS Redirect, Error Page, and Origin Access Control (OAC) to completely block direct S3 Bucket access from the Internet.
* **AWS Architecture Design Skills:**
    * Mastered rules for professional cloud system diagram representation, clearly defining spatial boundaries (Region, AZ, VPC, Public/Private Subnet) and Data Flows.
    * Fluently used the official AWS Architecture Icons set on Draw.io/Lucidchart tools.
    * Hands-on drew a complete, standard real-world AWS system architecture diagram: *"User -> CloudFront (Edge Location) -> Route 53 -> ALB (Public Subnet) -> EC2 Auto Scaling (Private Subnet) + S3 (Static Content)"*.
* **Backend Project Deployment:**
    * Successfully deployed API `GET /api/products` supporting pagination (limit, offset) and multi-criteria filters via query params (`category`, `brand`, `scent`, `min_price`).
    * Successfully deployed API `GET /api/products/{id}` (fetch detailed product information with scent notes) and API `DELETE /api/products/{id}` (delete product for Admin).
    * Deployed API `GET /api/search` supporting product search by name (`?q=name`) and optimized list query performance in Prisma ORM.
    * Constructed test cases to test all filters and pagination, and successfully completed testing the entire Product Management Module on Postman.
    * Completed detailed Prisma Schema design for Shopping Cart Module (Cart, CartItem) and Order Module (Order, OrderItem).