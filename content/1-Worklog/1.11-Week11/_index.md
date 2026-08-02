---
title: "Week 11 Worklog"
date: 2026-07-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

* **Capstone Project:** Completely design and deploy an enterprise-standard 3-Tier Web Architecture Model on AWS infrastructure.
* **System Architecture Integration:** Integrate multiple learned services (VPC, Subnets, ALB, EC2 ASG, RDS Multi-AZ, S3, CloudFront, CloudWatch) into a complete practical solution.
* **Security, Testing & Summary:** Strictly segment security across tiers, test automatic failover features (Failover), auto scaling under load (Auto Scaling), and finalize the internship report/worklog.

### Planned Tasks for This Week:
| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | ---- | ---------- | --------------- | ------------------- |
| Mon | - Analyze Traffic Flow and design detailed architecture diagram (CloudFront -> ALB -> EC2 ASG -> RDS Multi-AZ) <br> - Plan detailed IP ranges (VPC CIDR), list of Public/Private Subnets spread across 2 AZs, and define separate Security Groups for each tier | 10/08/2026 |  | [AWS 3-Tier Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-risk-and-compliance/architecting-for-the-cloud.html) |
| Tue | **Hands-on:** <br> - Initialize Custom Multi-AZ VPC (2 Public Subnets, 4 Private Subnets, IGW, Route Tables) <br> - Initialize DB Subnet Group and deploy Amazon RDS MySQL Instance (Multi-AZ configuration) placed entirely within a separate Private Subnet | 11/08/2026 |  | [AWS 3-Tier Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-risk-and-compliance/architecting-for-the-cloud.html) |
| Wed | **Hands-on:** <br> - Create Launch Template containing Web application source code and set up Auto Scaling Group (ASG) located in Private Subnet <br> - Initialize Application Load Balancer (ALB) in Public Subnet, configure Target Group, and route traffic safely to ASG | 12/08/2026 |  | [AWS 3-Tier Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-risk-and-compliance/architecting-for-the-cloud.html) |
| Thu | **Hands-on:** <br> - Configure Amazon CloudFront in front of ALB/S3 to accelerate distribution of static & dynamic data <br> - Build CloudWatch Dashboard monitoring EC2/RDS CPU/RAM performance and configure CloudWatch Alarm to send email alerts on failure | 13/08/2026 |  | [AWS 3-Tier Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-risk-and-compliance/architecting-for-the-cloud.html) |
| Fri | - **Failover Testing:** Simulate 1 AZ failure to test automatic service continuity capability of ALB & RDS Multi-AZ <br> - **Load Testing:** Run CPU stress testing tools to verify Auto-Scaling mechanism for auto scale-out servers <br> - Conduct project acceptance testing and finalize summary Worklog documentation report | 14/08/2026 |  | [AWS 3-Tier Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-risk-and-compliance/architecting-for-the-cloud.html) |

### Week 11 Results Achieved: