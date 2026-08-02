---
title: "Worklog Tuần 3"
date: 2024-06-15
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* **Lưu trữ đối tượng Amazon S3:** Nắm vững cấu trúc S3 Buckets, Objects, Storage Classes (Standard, IA, Glacier, Deep Archive).
* **Quản lý Vòng đời & Quản lý phiên bản:** Sử dụng S3 Versioning, Object Lock và thiết lập S3 Lifecycle Rules để tối ưu chi phí.
* **Bảo mật & Hosting Web tĩnh:** Cấu hình Bucket Policies, CORS, SSE Encryption và thực hành host trang Web tĩnh trên S3.
* **Project:** Khởi tạo repository, dựng môi trường phát triển với Docker, thiết lập Prisma ORM (Schema Auth Module, Migration, Seed data) và xây dựng khung Express server chuẩn hóa.

### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- |---------- | ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu Amazon S3 concept: <br>&emsp; +  Buckets <br>&emsp; +  Keys <br>&emsp; +  Metadata <br> - Phân biệt các S3 Storage Classes và mô hình chi phí  <br> - **Project:** <br>&emsp; + Tạo repository cho phần Backend trên GitHub <br>&emsp; + Dựng khung cấu trúc thư mục chuẩn cho dự án | 15/06/2026 | 15/06/2026 | [- Tổng quan về Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html) <br> [- Simple Storage Service (S3)](https://youtu.be/p9ddQvOoNQ4?si=Bpba8jaDgXIEXEfP)|
| 3   | - Tìm hiểu S3 Versioning & S3 Object Lock <br> - Cấu hình S3 Lifecycle Rules tự động chuyển vùng lưu trữ <br> - **Project:** <br>&emsp; + Khởi tạo Dockerfile và docker-compose.yml cho PostgreSQL và Node.js <br>&emsp; + Khởi tạo Prisma ORM và cấu hình biến môi trường .env (DATABASE_URL, PORT, JWT_SECRET, SMTP)| 16/06/2026 | 16/06/2026 | [Quản lý vòng đời S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html) |
| 4   | - Tìm hiểu cơ chế bảo mật S3: <br>&emsp; +  Bucket Policy <br>&emsp; +  IAM Policy <br> - Phương thức mã hóa S3: <br>&emsp; + SSE-S3 <br>&emsp; +  SSE-KMS <br> - **Project:** <br>&emsp; + Thiết kế Prisma Schema tổng quan cho Module Auth (User, Role, RefreshToken, PasswordResetOTP) <br>&emsp; + Viết script Migration khởi tạo cơ sở dữ liệu ban đầu | 17/06/2026 | 17/06/2026 | [Bảo mật & Chính sách S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-management.html) |
| 5   | - **Thực hành:** <br>&emsp; + Đóng gói ứng dụng Web (HTML/CSS/JS) <br>&emsp; + Cấu hình S3 Static Website Hosting kèm Bucket Policy cho phép Public Read  <br> - **Project:** <br>&emsp; + Viết script seed.js sử dụng Prisma Client tạo dữ liệu mẫu (Roles: Admin, Client và tài khoản Admin mặc định) <br>&emsp; + Thử nghiệm nạp dữ liệu vào Docker PostgreSQL qua lệnh npx prisma db seed| 18/06/2026 | 18/06/2026 | [Bật tính năng trang web tĩnh](https://000057.awsstudygroup.com/vi/3-staticwebsite/) |
| 6   | - Tìm hiểu về S3 Cross-Region Replication (CRR) <br> - **Project:** <br>&emsp; + Khởi tạo Express server, cấu hình Middleware xử lý lỗi tập trung <br>&emsp; + Chuẩn hóa cấu trúc Response (Success status: success, Error status: error) | 19/06/2026 | 19/06/2026 | [Hướng dẫn sao chép S3](https://000057.awsstudygroup.com/vi/10-s3ccr/) |

### Kết quả đạt được tuần 3:

* **Quản lý dữ liệu & Tối ưu chi phí S3:**
    * Hiểu rõ cấu trúc Buckets, Keys, Metadata và đặc tính từng lớp lưu trữ (Standard, IA, Glacier, Deep Archive).
    * Nắm vững cơ chế S3 Versioning, S3 Object Lock và thiết lập thành công S3 Lifecycle Rules để tự động chuyển vùng lưu trữ tối ưu chi phí.
    * Tìm hiểu nguyên lý hoạt động của S3 Cross-Region Replication (CRR).
* **Bảo mật & Thực hành Hosting S3:**
    * Viết thành công Bucket Policy phân quyền truy cập chặt chẽ, hiểu rõ sự khác biệt giữa IAM Policy và Bucket Policy.
    * Phân biệt và ứng dụng các phương thức mã hóa dữ liệu SSE-S3 và SSE-KMS.
    * Đóng gói ứng dụng web tĩnh (HTML/CSS/JS) và deploy thành công lên S3 Static Website Hosting kèm cấu hình Public Read Policy.
* **Triển khai Backend Project:**
    * Khởi tạo repository GitHub và thiết lập cấu trúc thư mục chuẩn cho dự án.
    * Đóng gói và khởi chạy thành công môi trường PostgreSQL và Node.js thông qua `Dockerfile` và `docker-compose.yml`.
    * Cấu hình Prisma ORM, hoàn tất thiết kế Prisma Schema cho Module Auth (User, Role, RefreshToken, PasswordResetOTP).
    * Chạy thành công script Migration khởi tạo cơ sở dữ liệu và nạp dữ liệu mẫu (Roles, tài khoản Admin mặc định) vào PostgreSQL qua `seed.js`.
    * Khởi tạo Express server, cài đặt hệ thống Middleware xử lý lỗi tập trung và chuẩn hóa cấu trúc API Response (`success` / `error`).
    