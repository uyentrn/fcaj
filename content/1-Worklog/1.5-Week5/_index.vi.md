---
title: "Worklog Tuần 5"
date: 2024-06-29
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* **Cơ sở dữ liệu quan hệ Amazon RDS:** Tìm hiểu RDS (MySQL/PostgreSQL), khái niệm Multi-AZ (High Availability) và Read Replicas (Scalability).
* **Cơ sở dữ liệu NoSQL Amazon DynamoDB:** Hiểu kiến trúc Key-Value/Document, Partition Key, Sort Key, Read/Write Capacity Units (RCU/WCU).
* **Thực hành triển khai Database:** Kết nối ứng dụng Web trên EC2 tới cơ sở dữ liệu RDS đặt trong Subnet riêng biệt.
* **Project:** Hoàn tất toàn bộ các API còn lại của Module Authentication (Logout, Forgot/Reset Password, User Profile), thực hiện kiểm thử tự động/độc lập và thiết kế Schema cơ sở dữ liệu chi tiết cho Module Quản lý sản phẩm.

### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- |---------- | ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu Amazon RDS và một số Database Engines được hỗ trợ <br>&emsp; + MySQL <br>&emsp; + PostgreDB <br> - So sánh Cơ chế đồng bộ Multi-AZ Deployment với cơ chế bất đồng bộ Read Replicas <br> - **Project:** <br>&emsp; + Viết API POST /api/auth/logout (đăng xuất/vô hiệu hóa phiên làm việc) <br>&emsp; + Viết API POST /api/auth/forgot-password (yêu cầu cấp mã OTP qua email để khôi phục mật khẩu) | 29/06/2026 | 29/06/2026 | [Amazon RDS Features](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html) |
| 3   | - Tìm hiểu Amazon DynamoDB (NoSQL) <br> - Phân tích cấu trúc dữ liệu: <br>&emsp; + Table <br>&emsp; +  Item <br>&emsp; + Attribute <br> - Phân biệt Partition Key (Simple Primary Key) và Composite Key (Partition Key + Sort Key) <br> - **Project:** <br>&emsp; + Viết API POST /api/auth/reset-password (xác thực OTP, đặt mật khẩu mới và đăng xuất tất cả các thiết bị) <br>&emsp; + Kiểm thử luồng khôi phục mật khẩu | 30/06/2026 | 30/06/2026 | [- DynamoDB Developer Guide](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html) <br> [- DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html)|
| 4   | - Tìm hiểu DynamoDB Provisioned và On-Demand Capacity Mode <br> - Tìm hiểu về Global Tables & DynamoDB Accelerator (DAX) <br> - **Project:** <br>&emsp; + Viết API GET /api/me (lấy thông tin của người dùng hiện tại) <br>&emsp; + Viết API PATCH /api/me (sửa thông tin người dùng hiện tại) | 01/07/2026 | 01/07/2026 | [- DynamoDB on-demand and provisioned capacity](https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/capacity.html) <br> [- DAX & Global Table](https://www.youtube.com/watch?v=HZLQbj3Cpyo)|
| 5   | - **Thực hành:** <br>&emsp; + Tạo DB Subnet Group <br>&emsp; + Khởi tạo RDS MySQL Instance Multi-AZ trong Private Subnet và kết nối từ EC2 Web Server <br> - **Project:** <br>&emsp; + Viết Unit Test cho luồng Đăng ký/Đăng nhập <br>&emsp; + Tạo Postman Collection và kiểm thử toàn bộ Module Authentication | 02/07/2026 | 02/07/2026 | [RDS Multi-AZ Tutorial](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateDBInstance.html) |
| 6   | - **Thực hành:** <br>&emsp; + Tạo một DynamoDB Table mới trên AWS Management Console với Partition Key cụ thể <br>&emsp; + Thực hiện các thao tác Thêm, Xem, Sửa, Xóa dữ liệu (CRUD) trực tiếp trên giao diện Console <br>&emsp; +  Sử dụng các câu lệnh `aws dynamodb put-item`, `aws dynamodb get-item`, `aws dynamodb scan` để thao tác dữ liệu từ lệnh CLI <br> - **Project:** Thiết kế Schema DB cho: <br>&emsp; + Danh mục / Nhóm mùi hương / Thương hiệu (Categories, Brands) <br>&emsp; + Sản phẩm, Biến thể sản phẩm và Note hương (Products, Product Variants, Attributes/Scent Notes)| 03/07/2026 | 03/07/2026 | [DynamoDB CLI Tutorial](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SampleData.html) |
### Kết quả đạt được tuần 5:
* **Amazon RDS (Relational Database Service):**
    * Phân biệt rõ ràng cơ chế nhân bản đồng bộ Multi-AZ Deployment (đảm bảo tính sẵn sàng cao High Availability và tự động Failover) và cơ chế nhân bản bất đồng bộ Read Replicas (tối ưu hiệu năng đọc và mở rộng Scalability).
    * Thực hành khởi tạo thành công DB Subnet Group và RDS MySQL Instance cấu hình Multi-AZ đặt hoàn toàn trong Private Subnet, đảm bảo chuẩn bảo mật không public ngoài Internet.
    * Đã kết nối an toàn ứng dụng Web trên EC2 tới RDS MySQL trong Subnet riêng biệt.
* **Amazon DynamoDB (NoSQL Database):**
    * Nắm vững các thành phần cốt lõi của DynamoDB (Table, Item, Attribute) và phân biệt Partition Key (Simple Primary Key) với Composite Key (Partition Key + Sort Key).
    * Phân biệt cơ chế Provisioned Capacity Mode và On-Demand Capacity Mode; hiểu nguyên lý hoạt động của Global Tables (đa vùng) và DynamoDB Accelerator - DAX (In-memory cache).
    * Thực hành khởi tạo DynamoDB Table trên AWS Console, thực hiện thành công các thao tác CRUD trực tiếp trên Console và sử dụng thành thạo các câu lệnh AWS CLI (`put-item`, `get-item`, `scan`).
* **Triển khai Backend Project:**
    * Viết và tích hợp thành công API `POST /api/auth/logout` (vô hiệu hóa phiên làm việc) và API `POST /api/auth/forgot-password` (yêu cầu cấp OTP khôi phục mật khẩu qua email).
    * Triển khai thành công API `POST /api/auth/reset-password` (xác thực OTP, đặt lại mật khẩu mới và tự động hủy tất cả các phiên đăng nhập trên mọi thiết bị).
    * Triển khai thành công bộ API Quản lý thông tin cá nhân: `GET /api/me` (lấy thông tin người dùng hiện tại) và `PATCH /api/me` (cập nhật thông tin cá nhân).
    * Viết Unit Test cho luồng Đăng ký/Đăng nhập, thiết lập Postman Collection và kiểm thử toàn diện toàn bộ luồng chức năng của Module Authentication.
    * Hoàn thành thiết kế Prisma Schema chi tiết cho Module Sản phẩm: Danh mục/Thương hiệu/Nhóm mùi hương (Categories, Brands), Sản phẩm & Biến thể sản phẩm (Products, Product Variants), và Thuộc tính/Note hương (Attributes/Scent Notes).
    