---
title: "Worklog Tuần 6"
date: 2024-07-06
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

* **Xử lý tính toán Serverless với AWS Lambda:** Nắm kiến trúc Event-driven, Lambda Execution Role, Triggers và Pricing model.
* **Cổng giao tiếp Amazon API Gateway:** Tìm hiểu REST API & HTTP API, cách tích hợp API Gateway với AWS Lambda và các dịch vụ backend.
* **Xây dựng ứng dụng Serverless:** Thực hành viết Serverless REST API đầy đủ tính năng CRUD kết hợp API Gateway, Lambda và DynamoDB.
* **Project:** Triển khai Migration Schema, khởi tạo dữ liệu mẫu (seed data) và xây dựng trọn bộ các API CRUD cho Danh mục (Categories), Thương hiệu (Brands) cùng sản phẩm/biến thể sản phẩm cho hệ thống.

### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- |---------- | ------------ | --------------- | -------------- |
| 2   | - Giới thiệu về Serverless Architecture <br> - Tìm hiểu AWS Lambda: <br>&emsp;+ Event Sources <br>&emsp;+ Execution Context <br>&emsp;+ Handler function <br> - **Project:** <br>&emsp; + Thực hiện Migration Schema sản phẩm vào cơ sở dữ liệu Docker <br>&emsp; + Cập nhật seed.js để khởi tạo dữ liệu mẫu cho danh mục, thương hiệu và sản phẩm nước hoa thử nghiệm | 06/07/2026 | 06/07/2026 | [- Serveless là gì? Ví dụ trên AWS Services](https://www.youtube.com/watch?v=9IjmBrBSGKs) <br> [- AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| 3   | - Tìm hiểu Amazon API Gateway: <br>&emsp;+ Resource <br>&emsp;+ Method <br>&emsp;+ Stages <br> - Phân biệt REST API, HTTP API và WebSocket API <br> - **Project:** <br>&emsp; + Viết API GET /api/categories (lấy danh sách nhóm mùi hương/thương hiệu) <br>&emsp; + Viết API POST /api/categories (tạo một nhóm mùi/thương hiệu mới cho Admin)| 07/07/2026 | 07/07/2026 | [Amazon API Gateway Overview](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html) |
| 4   | - Phân quyền cho Lambda bằng IAM Execution Role <br> - Quản lý Environment Variables, Timeout và Memory allocation <br> - **Project:** <br>&emsp; + Viết API PUT /api/categories/{id} (sửa thông tin một nhóm mùi hương/thương hiệu cụ thể cho Admin) <br>&emsp; + Viết API DELETE /api/categories/{id} (xóa một nhóm mùi hương/thương hiệu cụ thể cho Admin)| 08/07/2026 | 08/07/2026 | [Lambda Security & Permissions](https://docs.aws.amazon.com/lambda/latest/dg/lambda-permissions.html) |
| 5   | - **Thực hành:** Viết Lambda Function (Python/Node.js) nhận request từ API Gateway và thực hiện ghi dữ liệu vào DynamoDB <br> - **Project:** <br>&emsp; + Viết API GET /api/brand/{id} (lấy danh sách sản phẩm thuộc một brand cụ thể) <br>&emsp; + Kiểm thử trên Postman toàn bộ luồng quản lý Danh mục & Thương hiệu| 09/07/2026 | 09/07/2026 | [Tạo lambda function](https://000133.awsstudygroup.com/vi/2-create-lambda-functions/) |
| 6   | - **Thực hành:** Xây dựng hoàn chỉnh Serverless REST API (GET, POST, PUT, DELETE) qua API Gateway + Lambda + DynamoDB <br> - **Project:** <br>&emsp; + Viết API POST /api/products (tạo một sản phẩm mới bao gồm biến thể và note hương cho Admin) <br>&emsp; + Viết API PUT /api/products/{id} (thay đổi thông tin của một sản phẩm cho Admin)| 10/07/2026 | 10/07/2026 | [Video Hướng dẫn](https://www.youtube.com/watch?v=osuHIlAsnSc) |

### Kết quả đạt được tuần 6:
* **Tư duy & Kiến trúc Serverless với AWS Lambda:**
    * Thấu hiểu ưu điểm cốt lõi của Serverless: loại bỏ chi phí quản trị hạ tầng/OS, khả năng tự động mở rộng (Auto-scaling) theo số lượng request và mô hình tính chi phí tối ưu (chỉ trả tiền khi code thực thi).
    * Hiểu rõ cơ chế Event Sources, Execution Context, Handler function, cách cấu hình Environment Variables, Timeout và hạn mức bộ nhớ (Memory allocation).
    * Thiết lập thành công IAM Execution Role đảm bảo nguyên tắc phân quyền tối thiểu (Least Privilege) cho hàm Lambda khi tương tác với các dịch vụ khác.
* **Cổng giao tiếp Amazon API Gateway & Tích hợp:**
    * Nắm vững các khái niệm nền tảng trong API Gateway: Resource, Method, Stage, và phân biệt rõ trường hợp sử dụng giữa REST API, HTTP API và WebSocket API.
    * Thực hành kết nối thành công API Gateway làm điểm tiếp nhận request và kích hoạt (trigger) hàm Lambda xử lý logic nghiệp vụ.
    * Xây dựng và triển khai thành công ứng dụng Serverless REST API hoàn chỉnh hỗ trợ đầy đủ các thao tác CRUD (GET, POST, PUT, DELETE) kết hợp bộ ba API Gateway + Lambda + DynamoDB.
* **Triển khai Backend Project (Categories, Brands & Products):**
    * Chạy thành công Migration đưa Schema Sản phẩm vào CSDL Docker PostgreSQL; cập nhật `seed.js` tạo sẵn dữ liệu mẫu cho danh mục, thương hiệu và các sản phẩm nước hoa thử nghiệm.
    * Xây dựng trọn bộ API Quản lý Danh mục & Thương hiệu dành cho Admin/Client: `GET /api/categories` (lấy danh sách), `POST /api/categories` (tạo mới), `PUT /api/categories/{id}` (cập nhật) và `DELETE /api/categories/{id}` (xóa).
    * Triển khai API `GET /api/brand/{id}` lấy danh sách toàn bộ sản phẩm thuộc về một thương hiệu cụ thể và thực hiện kiểm thử thành công toàn bộ luồng trên Postman.
    * Xây dựng các API Quản lý Sản phẩm nâng cao dành cho Admin: `POST /api/products` (tạo mới sản phẩm kèm biến thể và danh sách note hương) và `PUT /api/products/{id}` (cập nhật thông tin chi tiết sản phẩm).