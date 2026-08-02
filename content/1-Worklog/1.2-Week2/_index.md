---
title: "Week 2 Worklog"
date: 2024-06-08
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* **Amazon VPC Concepts:** Master core AWS networking components including Virtual Private Cloud (VPC), Subnet (Public & Private), and IPv4 CIDR Blocks.
* **Basic Network Routing & Security:** Clearly understand the functions of Internet Gateway (IGW), Route Table, Security Group (Stateful), and Network ACL (Stateless).
* **Hands-on Custom VPC Design:** Manually create a complete custom VPC network infrastructure and deploy an EC2 instance in a Public Subnet.
* **Project:** Reach a consensus on the topic and allocate tasks among team members.

### Tasks Implemented This Week:
| Day | Task | Start Date | Completion Date | Reference Materials |
| --- |----- | ---------- | --------------- | ------------------- |
| Mon | - Learn about Amazon VPC concepts, CIDR Notation (/16, /24) <br> - Differentiate between Public Subnet and Private Subnet <br> - Research and select feasible topics for the project | 08/06/2026 | 08/06/2026 | [AWS VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| Tue | - Learn about Internet Gateway (IGW) <br> - Configure Route Tables for Public Subnet and Private Subnet | 09/06/2026 | 09/06/2026 | [Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) |
| Wed | - Differentiate Security Group (SG) and Network ACL (NACL) <br> - Learn about Stateful vs Stateless mechanisms in VPC | 10/06/2026 | 10/06/2026 | [SGs vs NACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-basics.html) |
| Thu | - **Hands-on:** Create a Custom VPC (10.0.0.0/16) consisting of 2 Public Subnets and 2 Private Subnets located across 2 different AZs | 11/06/2026 | 11/06/2026 | [VPC Workshop](https://000003.awsstudygroup.com/vi/3-prerequisite/) |
| Fri | - **Hands-on:** Launch an EC2 instance in Public Subnet, assign Elastic IP, configure Security Group to allow SSH & HTTP, and verify connection | 12/06/2026 | 12/06/2026 | [Deploy Amazon EC2 Instances](https://000003.awsstudygroup.com/vi/4-createec2server/)|

### Week 2 Results Achieved:

* **AWS Networking:** Deeply understood IP addresses/CIDR and standard Subnetting design on the cloud.
* **Security & Routing:** Differentiated the operation mechanisms between SGs and NACLs; learned how to route Internet-bound traffic via IGW.
* **Hands-on:** Successfully created a complete Custom VPC spread across 2 AZs and verified Public EC2 connectivity successfully.
* **Project:** Selected the project topic: an e-commerce web application for selling perfume. Assumed the role of Backend Developer.