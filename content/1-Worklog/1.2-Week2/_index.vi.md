---
title: "Worklog Tuần 2"
date: 2024-06-08
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* **Khái niệm Amazon VPC:** Nắm vững các thành phần mạng cơ bản trong AWS bao gồm Virtual Private Cloud (VPC), Subnet (Public & Private), IPv4 CIDR Blocks.
* **Định tuyến & Bảo mật mạng cơ bản:** Hiểu rõ chức năng của Internet Gateway (IGW), Route Table, Security Group (Stateful) và Network ACL (Stateless).
* **Thực hành thiết kế Custom VPC:** Tự tay khởi tạo một hạ tầng mạng VPC tùy chỉnh hoàn chỉnh và triển khai máy chủ EC2 trong Public Subnet.
* **Project:** Thống nhất về chủ đề và phân chia công việc với các thành viên trong nhóm.

### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- |---------- | ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu khái niệm Amazon VPC, CIDR Notation (/16, /24) <br> - Phân biệt Public Subnet và Private Subnet <br> - Tìm hiểu và chọn những chủ đề khả thi cho project| 08/06/2026 | 08/06/2026 | [AWS VPC](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) |
| 3   | - Tìm hiểu Internet Gateway (IGW) <br> - Cấu hình Route Table cho Public Subnet và Private Subnet | 09/06/2026 | 09/06/2026 | [Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) |
| 4   | - Phân biệt Security Group (SG) và Network ACL (NACL) <br> - Tìm hiểu cơ chế Stateful vs Stateless trong VPC | 10/06/2026 | 10/06/2026 | [SGs vs NACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-basics.html) |
| 5   | - **Thực hành:** Tạo Custom VPC (10.0.0.0/16) gồm 2 Public Subnets và 2 Private Subnets nằm ở 2 AZs khác nhau | 11/06/2026 | 11/06/2026 | [VPC Workshop](https://000003.awsstudygroup.com/vi/3-prerequisite/) |
| 6   | - **Thực hành:** Khởi tạo EC2 trong Public Subnet, gán Elastic IP, cấu hình Security Group cho phép SSH & HTTP và kiểm tra kết nối | 12/06/2026 | 12/06/2026 | [Triển khai Amazon EC2 Instances](https://000003.awsstudygroup.com/vi/4-createec2server/)|

### Kết quả đạt được tuần 2:

* **Mạng AWS:** Hiểu sâu về địa chỉ IP/CIDR và cách chia Subnet chuẩn thiết kế trên đám mây.
* **Bảo mật & Định tuyến:** Phân biệt được cơ chế hoạt động của SG và NACL; biết cách định tuyến traffic ra Internet qua IGW.
* **Thực hành:** Khởi tạo thành công 1 Custom VPC hoàn chỉnh rải trên 2 AZs và kiểm tra kết nối EC2 Public thành công.
* **Project:** Chọn chủ đề về ứng dụng web thương mại điện tử bán nước hoa. Đảm nhận vai trò Backend Developer.