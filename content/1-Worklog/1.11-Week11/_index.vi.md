---
title: "Worklog Tuần 11"
date: 2026-07-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* **Dự án Tổng hợp (Capstone Project):** Thiết kế và triển khai hoàn chỉnh Mô hình Kiến trúc Web 3 Lớp (3-Tier Web Architecture) chuẩn doanh nghiệp trên hạ tầng AWS.
* **Tích hợp Kiến trúc Hệ thống:** Tích hợp đa dịch vụ đã học (VPC, Subnets, ALB, EC2 ASG, RDS Multi-AZ, S3, CloudFront, CloudWatch) thành một giải pháp thực tế hoàn chỉnh.
* **Bảo mật, Kiểm thử & Tổng kết:** Phân tầng bảo mật nghiêm ngặt giữa các lớp, kiểm thử tính năng chuyển vùng sự cố tự động (Failover), tính năng tự động mở rộng tải (Auto Scaling) và hoàn thiện báo cáo thực tập/worklog.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ----------| ------------ | --------------- | -------------- |
| 2   | - Phân tích luồng dữ liệu (Traffic Flow) và thiết kế bản vẽ sơ đồ kiến trúc chi tiết (CloudFront -> ALB -> EC2 ASG -> RDS Multi-AZ) <br> - Quy hoạch chi tiết dải IP (VPC CIDR), danh sách Public/Private Subnets rải trên 2 AZs và định nghĩa các nhóm Security Group riêng biệt cho từng tầng | 10/08/2026 |  | [AWS 3-Tier Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-risk-and-compliance/architecting-for-the-cloud.html) |
| 3   | **Thực hành:** <br> - Khởi tạo Custom VPC Multi-AZ (2 Public Subnets, 4 Private Subnets, IGW, Route Tables) <br> - Khởi tạo DB Subnet Group và triển khai Amazon RDS MySQL Instance (cấu hình Multi-AZ) nằm gọn trong Private Subnet riêng biệt | 11/08/2026 |  | [AWS 3-Tier Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-risk-and-compliance/architecting-for-the-cloud.html) |
| 4   | **Thực hành:** <br> - Tạo Launch Template chứa mã nguồn ứng dụng Web và thiết lập Auto Scaling Group (ASG) đặt tại Private Subnet <br> - Khởi tạo Application Load Balancer (ALB) nằm ở Public Subnet, cấu hình Target Group và điều hướng traffic an toàn tới ASG | 12/08/2026 |  | [AWS 3-Tier Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-risk-and-compliance/architecting-for-the-cloud.html) |
| 5   | **Thực hành:** <br> - Cấu hình Amazon CloudFront đứng trước ALB/S3 để tăng tốc phân phối dữ liệu tĩnh & động <br> - Dựng CloudWatch Dashboard theo dõi hiệu năng CPU/RAM của EC2/RDS và cấu hình CloudWatch Alarm phát cảnh báo về Email khi có sự cố | 13/08/2026 |  | [AWS 3-Tier Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-risk-and-compliance/architecting-for-the-cloud.html) |
| 6   | - **Kiểm thử Failover:** Mô phỏng đứt gãy 1 AZ để kiểm tra khả năng tự động duy trì dịch vụ của ALB & RDS Multi-AZ <br> - **Kiểm thử Tải:** Chạy tool ép tải CPU để verify cơ chế Auto-Scaling tự scale-out máy chủ <br> - Nghiệm thu toàn bộ dự án và hoàn tất tài liệu báo cáo Worklog tổng kết | 14/08/2026 |  | [AWS 3-Tier Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/aws-risk-and-compliance/architecting-for-the-cloud.html) |

### Kết quả đạt được tuần 11:

