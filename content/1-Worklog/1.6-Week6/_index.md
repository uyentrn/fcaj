---
title: "Week 6 Worklog"
date: 2024-07-06
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* **Serverless Compute Processing with AWS Lambda:** Master Event-driven architecture, Lambda Execution Role, Triggers, and Pricing model.
* **Amazon API Gateway:** Learn REST API & HTTP API, how to integrate API Gateway with AWS Lambda and backend services.
* **Building Serverless Applications:** Practice building a fully featured Serverless REST API supporting CRUD operations combining API Gateway, Lambda, and DynamoDB.
* **Project:** Deploy Schema Migration, initialize seed data, and build a full set of CRUD APIs for Categories, Brands, along with products/product variants for the system.

### Tasks Implemented This Week:
| Day | Task | Start Date | Completion Date | Reference Materials |
| --- |----- | ---------- | --------------- | ------------------- |
| Mon | - Introduction to Serverless Architecture <br> - Learn about AWS Lambda: <br>&emsp;+ Event Sources <br>&emsp;+ Execution Context <br>&emsp;+ Handler function <br> - **Project:** <br>&emsp; + Perform Product Schema Migration into Docker database <br>&emsp; + Update seed.js to initialize sample data for categories, brands, and test perfume products | 06/07/2026 | 06/07/2026 | [- What is Serverless? Examples on AWS Services](https://www.youtube.com/watch?v=9IjmBrBSGKs) <br> [- AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Tue | - Learn about Amazon API Gateway: <br>&emsp;+ Resource <br>&emsp;+ Method <br>&emsp;+ Stages <br> - Differentiate REST API, HTTP API, and WebSocket API <br> - **Project:** <br>&emsp; + Write API GET /api/categories (get list of scent families/brands) <br>&emsp; + Write API POST /api/categories (create a new scent family/brand for Admin) | 07/07/2026 | 07/07/2026 | [Amazon API Gateway Overview](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html) |
| Wed | - Grant permissions to Lambda using IAM Execution Role <br> - Manage Environment Variables, Timeout, and Memory allocation <br> - **Project:** <br>&emsp; + Write API PUT /api/categories/{id} (edit information of a specific scent family/brand for Admin) <br>&emsp; + Write API DELETE /api/categories/{id} (delete a specific scent family/brand for Admin) | 08/07/2026 | 08/07/2026 | [Lambda Security & Permissions](https://docs.aws.amazon.com/lambda/latest/dg/lambda-permissions.html) |
| Thu | - **Hands-on:** Write Lambda Function (Python/Node.js) receiving requests from API Gateway and performing data writes to DynamoDB <br> - **Project:** <br>&emsp; + Write API GET /api/brand/{id} (get list of products belonging to a specific brand) <br>&emsp; + Test the entire Category & Brand management flow on Postman | 09/07/2026 | 09/07/2026 | [Create lambda function](https://000133.awsstudygroup.com/vi/2-create-lambda-functions/) |
| Fri | - **Hands-on:** Build a complete Serverless REST API (GET, POST, PUT, DELETE) via API Gateway + Lambda + DynamoDB <br> - **Project:** <br>&emsp; + Write API POST /api/products (create a new product including variants and scent notes for Admin) <br>&emsp; + Write API PUT /api/products/{id} (update information of a product for Admin) | 10/07/2026 | 10/07/2026 | [Video Tutorial](https://www.youtube.com/watch?v=osuHIlAsnSc) |

### Week 6 Results Achieved:
* **Serverless Thinking & Architecture with AWS Lambda:**
    * Thoroughly understood core advantages of Serverless: eliminating infrastructure/OS management overhead, automatic scaling based on request volume, and an optimized pricing model (pay only for execution time).
    * Clearly understood Event Sources, Execution Context, Handler functions, as well as how to configure Environment Variables, Timeout, and Memory allocation limits.
    * Successfully established IAM Execution Role ensuring the principle of least privilege (Least Privilege) for Lambda functions when interacting with other services.
* **Amazon API Gateway & Integration:**
    * Mastered foundational concepts in API Gateway: Resource, Method, Stage, and clearly differentiated use cases among REST API, HTTP API, and WebSocket API.
    * Successfully practiced connecting API Gateway as an entry point for receiving requests and triggering Lambda functions to process business logic.
    * Built and successfully deployed a complete Serverless REST API supporting full CRUD operations (GET, POST, PUT, DELETE) combining the trio of API Gateway + Lambda + DynamoDB.
* **Backend Project Deployment (Categories, Brands & Products):**
    * Successfully ran Migration applying Product Schema to Docker PostgreSQL DB; updated `seed.js` to pre-populate sample data for categories, brands, and test perfume products.
    * Built a full set of Category & Brand Management APIs for Admin/Client: `GET /api/categories` (get list), `POST /api/categories` (create new), `PUT /api/categories/{id}` (update), and `DELETE /api/categories/{id}` (delete).
    * Deployed API `GET /api/brand/{id}` to fetch all products belonging to a specific brand and successfully tested the full flow on Postman.
    * Built advanced Product Management APIs for Admin: `POST /api/products` (create new product with variants and scent notes list) and `PUT /api/products/{id}` (update detailed product information).