---
title: "Worklog Tuần 8"
date: 2026-07-20
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Hiểu tư duy Đóng gói ứng dụng (Containerization) với Docker trong phát triển phần mềm.
* Thành thạo cách đóng gói, tối ưu Dockerfile và đẩy Docker Image lên kho lưu trữ AWS ECR (Elastic Container Registry).
* Triển khai ứng dụng Web từ Container lên AWS bằng dịch vụ AWS App Runner đơn giản, tự động.
* Cấu hình cơ chế Tự động hóa triển khai (Auto-deploy) và các thông số vận hành (Environment Variables, Scaling, Health Check, Domain Custom) trên AWS App Runner.
* Đánh giá, tổng kết chi phí và tối ưu hóa tài nguyên thử nghiệm trên AWS.
* **Project:** Triển khai trọn bộ API Quản lý Giỏ hàng, luồng Checkout tạo đơn hàng áp dụng Database Transaction, hệ thống tự động gửi email thông báo đơn hàng/trạng thái và các API Quản lý Đơn hàng nâng cao dành cho Admin.


### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ----------| ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu khái niệm Containerization & So sánh Docker với Virtual Machine (EC2) <br> - Viết `Dockerfile` đơn giản để đóng gói một ứng dụng Web (Node.js/Python/React) <br> - **Project:** <br>&emsp; + Viết API GET /api/cart (lấy giỏ hàng của người dùng hiện tại cho Client) <br>&emsp; + Viết API POST /api/cart (thêm sản phẩm vào giỏ hàng với variant_id, quantity cho Client) | 20/07/2026 | 20/07/2026 | [Learn Docker & Deploy to AWS (Beginner Tutorial)](https://www.youtube.com/watch?v=1_AlV-FFxM8&t=575s) |
| 3   | - Tìm hiểu dịch vụ AWS ECR (Kho chứa Docker Image) <br> - **Thực hành:** Tạo Repository trên ECR, dùng AWS CLI đăng nhập và push Docker Image lên ECR <br> - **Project:** <br>&emsp; + Viết API PUT /api/cart/{itemId} (cập nhật số lượng sản phẩm trong giỏ hàng cho Client) <br>&emsp; + Viết API DELETE /api/cart/{itemId} (xóa sản phẩm khỏi giỏ hàng cho Client)| 21/07/2026 | 21/07/2026 | [- Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html) <br> [- Push docker to Amazon ECR](https://www.youtube.com/watch?v=OaSxs2uqipQ) |
| 4   | - Tìm hiểu dịch vụ AWS App Runner (Dịch vụ chạy Container tự động dành cho Software Developer không cần quản lý hạ tầng) <br> - **Thực hành:** Cấu hình App Runner pull image từ ECR và tự động Deploy ứng dụng Web ra internet <br> - **Project:** <br>&emsp; + Kiểm thử luồng quản lý Giỏ hàng trên Postman <br>&emsp; + Xử lý các trường hợp biên (sản phẩm hết hàng, cập nhật số lượng vượt tồn kho) | 22/07/2026 | 22/07/2026 | [- AWS App Runner](https://docs.aws.amazon.com/apprunner/latest/dg/what-is-apprunner.html) <br> [- Deploying Next.js on AWS App Runner](https://www.youtube.com/watch?v=XMIgCgkzhfk) |
| 5   | - **Project:** <br>&emsp; + Viết API POST /api/orders (Checkout: chuyển giỏ hàng thành đơn hàng cho Client áp dụng Database Transaction) <br>&emsp; + Viết API POST /api/orders/checkout (tạo đơn hàng mới từ giỏ hàng hiện tại) + Tích hợp tự động kích hoạt gửi email thông báo đơn hàng đang chờ xác nhận cho Client <br>&emsp; + Viết API GET /api/admin/orders (xem lịch sử đơn hàng của tất cả người dùng cho Admin) <br>&emsp; + Viết API GET /api/admin/orders/:id (xem chi tiết hoặc trạng thái đơn hàng cụ thể cho Admin)| 23/07/2026 | 23/07/2026 | |
| 6   | - Tìm hiểu Amazon CloudWatch Metrics, Dashboards <br> - Tìm hiểu về cách thiết lập CloudWatch Alarms gửi cảnh báo qua Amazon SNS <br> - **Project:** <br>&emsp; + Viết API PATCH /api/admin/orders/{id} (cập nhật trạng thái đơn hàng: paid, shipping, completed, cancelled) <br>&emsp; + Triển khai tự động gửi email thông báo trạng thái mới cho khách hàng khi Admin cập nhật | 24/07/2026 | 24/07/2026 | [- Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) <br> [- How To Create a CloudWatch Dashboard](https://www.youtube.com/watch?v=5QK3FB1EsV0)|


### Kết quả đạt được tuần 8:
* **Containerization & AWS ECR:**
    * Thấu hiểu sự khác biệt giữa Containerization (Docker) và Virtual Machine (EC2), nắm vững tư duy đóng gói ứng dụng độc lập môi trường.
    * Đóng gói thành công ứng dụng Web thành Docker Image chuẩn và tối ưu hóa kích thước image bằng kỹ thuật Multi-stage build.
    * Tạo ECR Repository, sử dụng thành thạo AWS CLI để xác thực, đẩy (push) và quản lý phân phiên bản (tagging) Docker Images an toàn trên kho lưu trữ AWS ECR.
* **AWS App Runner & Giám sát Hệ thống (CloudWatch):**
    * Nắm vững kiến thức về AWS App Runner - giải pháp PaaS/Serverless Container giúp triển khai ứng dụng tự động không cần quản lý hạ tầng máy chủ.
    * Cấu hình App Runner pull image trực tiếp từ ECR và triển khai thành công ứng dụng Web ra Internet kèm thiết lập cơ chế Tự động hóa triển khai (Auto-deploy) khi có bản build mới.
    * Nắm vững cách quản lý biến môi trường, thiết lập Health Check và kiểm soát chi phí tài nguyên Cloud.
    * Tìm hiểu cấu hình Amazon CloudWatch Metrics, Dashboards và cơ chế thiết lập CloudWatch Alarms gửi cảnh báo tự động qua Amazon SNS.
* **Triển khai Backend Project (Cart & Order Modules):**
    * Triển khai trọn bộ API Quản lý Giỏ hàng cho Client: `GET /api/cart` (lấy giỏ hàng hiện tại), `POST /api/cart` (thêm sản phẩm vào giỏ với `variant_id` và `quantity`), `PUT /api/cart/{itemId}` (cập nhật số lượng) và `DELETE /api/cart/{itemId}` (xóa sản phẩm khỏi giỏ).
    * Xử lý triệt để các trường hợp biên trong quản lý giỏ hàng (sản phẩm hết hàng, số lượng cập nhật vượt quá tồn kho) và kiểm thử toàn diện trên Postman.
    * Triển khai API Checkout `POST /api/orders` & `POST /api/orders/checkout` tạo đơn hàng từ giỏ hàng hiện tại, áp dụng **Database Transaction** để bảo đảm tính toàn vẹn dữ liệu (trừ tồn kho, xóa giỏ hàng) và tích hợp tự động gửi email thông báo xác nhận đơn hàng cho Client.
    * Triển khai bộ API Quản lý Đơn hàng cho Admin: `GET /api/admin/orders` (xem danh sách tất cả đơn hàng), `GET /api/admin/orders/{id}` (xem chi tiết đơn hàng) và `PATCH /api/admin/orders/{id}` (cập nhật trạng thái đơn hàng: `paid`, `shipping`, `completed`, `cancelled`).
    * Tích hợp cơ chế tự động kích hoạt gửi email thông báo cập nhật trạng thái đơn hàng mới cho khách hàng mỗi khi Admin thay đổi trạng thái đơn.