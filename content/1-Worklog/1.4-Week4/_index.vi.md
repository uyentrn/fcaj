---
title: "Worklog Tuần 4"
date: 2024-06-22
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* **Cân bằng tải Elastic Load Balancing (ELB):** Tìm hiểu Application Load Balancer (ALB) Layer 7 & Network Load Balancer (NLB) Layer 4, Target Groups và Health Checks.
* **Tự động mở rộng Auto Scaling Group (ASG):** Nắm chắc khái niệm Launch Template, Auto Scaling Policies (Target Tracking, Step Scaling).
* **Kiến trúc High Availability:** Kết hợp ALB + ASG để xây dựng hệ thống tự động điều tiết tài nguyên máy chủ theo nhu cầu thực tế.
* **Project:** Tích hợp dịch vụ email SMTP, xây dựng hoàn chỉnh các API thuộc luồng xác thực (Request OTP, Register, Login, Refresh Token) và triển khai các Middleware an ninh (JWT Authentication, RBAC Authorization, Refresh Token Rotation).
### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- |---------- | ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu Elastic Load Balancing: <br>&emsp; + ALB <br>&emsp; +  NLB <br>&emsp; +  GWLB. <br> - Tìm hiểu về các thuật toán Routings và Health Checks  <br> - **Project:** <br>&emsp; + Tích hợp dịch vụ gửi Email thông qua dichj vụ SMTP <br>&emsp; + Xây dựng email helper để gửi mã xác nhận và thông báo hệ thống| 22/06/2026 | 22/06/2026 | [- Master All 3 AWS Load Balancers](https://www.youtube.com/watch?v=znQsN8KzF_o) <br> [- AWS Application Load Balancer - Routing Algorithms and Health Checking](https://www.youtube.com/watch?v=oRz4Ln1zOLg)|
| 3   | - Tìm hiểu Auto Scaling Group (ASG) <br> - Phân biệt Launch Configuration và Launch Template <br> - **Project:** <br>&emsp; + Viết API POST /api/auth/request-register-otp (gửi mã OTP 6 số đến email đăng ký) <br>&emsp; + Kiểm thử gửi OTP thành công qua SMTP | 23/06/2026 | 23/06/2026 | [Auto Scaling Groups](https://docs.aws.amazon.com/autoscaling/ec2/userguide/AutoScalingGroup.html) |
| 4   | - Tìm hiểu các chính sách Dynamic Scaling: <br>&emsp; +  Target Tracking <br>&emsp; +  Dynamic Scaling Policy <br>&emsp; +  Scheduled Scaling  <br> - **Project:** <br>&emsp; + Viết API POST /api/auth/register (đăng ký tài khoản người dùng mới sau khi xác thực OTP) <br>&emsp; + Triển khai mã hóa mật khẩu an toàn (Bcrypt/Argon2)| 24/06/2026 | 24/06/2026 | [Scaling Policies](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scale-based-on-demand.html) |
| 5   | - **Thực hành:** Tạo Application Load Balancer (ALB) điều hướng traffic tới 2 EC2 Web Servers chạy ở 2 AZs <br> - **Project:** <br>&emsp; + Viết API POST /api/auth/login (đăng nhập, trả về Access Token & Refresh Token) <br>&emsp; + Viết API POST /api/auth/refresh (làm mới Access Token) | 25/06/2026 | 25/06/2026 | [How to Create AWS Application Load Balancer(ALB)](https://www.youtube.com/watch?v=xJkWrEsT2Vs) |
| 6   | - **Thực hành:** <br>&emsp; + Tạo Launch Template từ AMI, dựng ASG (Min: 2, Desired: 2, Max: 4) gắn liền ALB <br>&emsp; + Cấu hình auto scaling policy & test việc auto-scale  <br> - **Project:** <br>&emsp; + Xây dựng Middleware xác thực JWT Check và Refresh Token rotation <br>&emsp; + Triển khai Middleware phân quyền (RBAC: Admin, Client)| 26/06/2026 | 26/06/2026 | [ Auto Scaling Group (complete guide)](https://www.youtube.com/watch?v=ysIRuF7XQbk) |

### Kết quả đạt được tuần 4:

* **Elastic Load Balancing (ELB) & High Availability:**
    * Phân biệt rõ tính năng và trường hợp sử dụng của Application Load Balancer (Layer 7), Network Load Balancer (Layer 4) và Gateway Load Balancer.
    * Nắm vững các thuật toán Routing và cấu hình Health Check để tự động điều hướng traffic an toàn đến các instance lành lặn.
    * Thực hành khởi tạo thành công ALB điều hướng traffic cân bằng tới 2 EC2 Web Servers nằm ở 2 Availability Zones (AZs) khác nhau.
* **Auto Scaling Group (ASG) & Auto-Scaling:**
    * Phân biệt Launch Configuration và Launch Template; hiểu rõ các chính sách mở rộng linh hoạt (Target Tracking, Dynamic Scaling, Scheduled Scaling).
    * Tạo thành công Launch Template từ AMI, khởi tạo ASG (Min: 2, Desired: 2, Max: 4) kết nối trực tiếp với ALB.
    * Kiểm thử thành công khả năng tự động mở rộng (auto-scale) tài nguyên máy chủ dưới áp lực tải lớn và cơ chế tự động thay thế các instance bị lỗi (Unhealthy).
* **Triển khai Backend Project (Auth Module):**
    * Tích hợp thành công dịch vụ SMTP và xây dựng helper gửi email tự động (mã xác nhận OTP, thông báo hệ thống).
    * Triển khai hoàn thiện API `POST /api/auth/request-register-otp` (tạo và gửi OTP 6 số qua email) kèm kiểm thử thành công gửi thư.
    * Triển khai hoàn thiện API `POST /api/auth/register` (đăng ký tài khoản sau khi xác thực OTP) tích hợp mã hóa mật khẩu an toàn với Bcrypt/Argon2.
    * Triển khai hoàn thiện API `POST /api/auth/login` (xác thực và cấp phát Access Token & Refresh Token) và API `POST /api/auth/refresh` (làm mới Access Token).
    * Viết và tích hợp thành công Middleware kiểm tra JWT Check, cơ chế Refresh Token rotation chống gian lận token và Middleware phân quyền dựa trên vai trò (RBAC: Admin, Client).
