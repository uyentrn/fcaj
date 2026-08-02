---
title: "Worklog Tuần 7"
date: 2024-07-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* **Mạng lưới phân phối nội dung (Amazon CloudFront - CDN):** Nắm vững kiến trúc mạng lưới trạm Edge Locations, cơ chế Caching, Origin Access Control (OAC), Invalidation và các phương thức bảo mật HTTPS/SSL với AWS Certificate Manager (ACM).
* **Tích hợp CDN với Hạ tầng AWS:** Triển khai CloudFront làm lớp tăng tốc & bảo mật đứng trước S3 Bucket (Static Web/Assets) và Application Load Balancer / API Gateway (Dynamic Traffic).
* **Thiết kế & Biểu diễn Kiến trúc:** Thành thạo cách dùng bộ icon chuẩn AWS (AWS Architecture Icons v2024/2025), quy tắc vẽ ranh giới (Region, AZ, VPC, Subnet) và thiết kế được bản vẽ sơ đồ kiến trúc hoàn chỉnh cho dự án cơ bản có sử dụng CDN.
* **Project:** Hoàn thiện bộ API xem chi tiết, xóa, phân trang, lọc đa tiêu chí, tìm kiếm sản phẩm và thiết kế Schema cơ sở dữ liệu cho Module Cart và Order.

### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- |---------- | ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu về Amazon CloudFront (CDN), vai trò của Edge Locations/ Edge Caching trong việc giảm độ trễ (latency) <br> - Phân tích cấu trúc CloudFront Distribution: Origin (S3, ALB, Custom Origin) & Behavior <br> - **Project:** <br>&emsp; + Viết API GET /api/products (lấy danh sách sản phẩm hỗ trợ phân trang limit, offset) <br>&emsp; + Xây dựng bộ lọc cho sản phẩm theo query params: category, brand, scent, min_price| 13/07/2026 | 13/07/2026 | [Amazon CloudFront Developer Guide](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html) |
| 3   | - Tìm hiểu cơ chế bảo mật Origin Access Control (OAC) ngăn người dùng truy cập trực tiếp vào S3 <br> - Tìm hiểu về cơ chế Caching Policies, TTL (Time-To-Live) và kỹ thuật CloudFront Invalidation (xóa cache thủ công) <br> - **Project:** <br>&emsp; + Viết API GET /api/products/{id} (lấy thông tin chi tiết của một loại nước hoa bao gồm các note hương) <br>&emsp; + Viết API DELETE /api/products/{id} (xóa một sản phẩm cho Admin)| 14/07/2026 | 14/07/2026 | [- OAC](https://www.youtube.com/watch?v=KtWFGnB_dOs) <br> [- CloudFront Caching & Security](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Expiration.html) |
| 4   | - Tìm hiểu về phương thức mã hóa SSL/TLS qua AWS Certificate Manager (ACM) và tích hợp bảo mật chống tấn công DDoS (AWS WAF & Shield) <br> - **Project:** <br>&emsp; + Viết API GET /api/search (tìm kiếm sản phẩm theo tên với query string ?q=name) <br>&emsp; + Tối ưu hóa hiệu năng truy vấn danh sách sản phẩm trong Prisma| 15/07/2026 | 15/07/2026 | [- AWS Certificate Manager Tutorial](https://www.youtube.com/watch?v=dGciSbEfx3k) <br> [- AWS WAF](https://www.youtube.com/watch?v=u6lQo0SIJMc) |
| 5   | - **Thực hành:** <br>&emsp; + Kiểm tra website trên S3, tạo CloudFront distribution, cấu hình HTTPS redirect, caching, error page <br>&emsp; + Thiết lập Origin Access Control để ngăn truy cập trực tiếp vào bucket S3 <br> - **Project:** <br>&emsp; + Kiểm thử đầy đủ các endpoint thuộc Module Product Management trên Postman <br>&emsp; + Viết Test case cho các bộ lọc tìm kiếm và phân trang sản phẩm | 16/07/2026 | 16/07/2026 | [Host một website tĩnh kết hợp CloudFront and S3](https://www.youtube.com/watch?v=9X2IXN64ZLY) |
| 6   | - Tìm hiểu về cách vẽ một kiến trúc chuẩn AWS: <br>&emsp; + Luồng dữ liệu <br>&emsp; + Ranh giới AWS Global/ Region/ Edge Location/ VPC/ Subnet <br> - Sử dụng công cụ Draw.io / Lucidchart với bộ icon chính thức **AWS Architecture Icons** <br> - **Thực hành:** Vẽ kiến trúc hệ thống chuẩn gồm *"User -> CloudFront (Edge Location) -> Route 53 -> ALB (Public Subnet) -> EC2 Auto Scaling (Private Subnet) + S3 (Static Content)"* <br> - **Project:** Thiết kế Schema DB cho: <br>&emsp; + Giỏ hàng (Cart, CartItem) <br>&emsp; + Đơn hàng (Order, OrderItem)| 17/07/2026 | 17/07/2026 | [- AWS Architecture Icons](https://aws.amazon.com/architecture/icons/) <br> [- Hướng dẫn vẽ kiến trúc AWS trên draw.io](https://www.youtube.com/watch?v=l8isyDe-GwY&t=2091s) |

### Kết quả đạt được tuần 7:

* **Mạng lưới phân phối CloudFront (CDN) & Bảo mật:**
    * Thấu hiểu vai trò của Edge Locations/Edge Caching trong việc giảm độ trễ (latency) toàn cầu và giảm tải tài nguyên cho gốc (Origin).
    * Hiểu rõ cấu trúc CloudFront Distribution, phân biệt các dạng Origin (S3, ALB, Custom Origin) và cấu hình Cache Behavior riêng cho nội dung tĩnh và động.
    * Nắm vững cơ chế Caching Policies, TTL (Time-To-Live) và kỹ thuật CloudFront Invalidation để xóa cache thủ công khi cập nhật nội dung.
    * Hiểu sâu về phương thức mã hóa HTTPS/SSL qua AWS Certificate Manager (ACM) cũng như giải pháp bảo mật chống tấn công DDoS (AWS WAF & Shield).
    * Thực hành khởi tạo thành công CloudFront Distribution cho website tĩnh trên S3, thiết lập cấu hình HTTPS Redirect, Error Page và Origin Access Control (OAC) chặn hoàn toàn truy cập trực tiếp vào S3 Bucket từ ngoài Internet.
* **Kỹ năng Thiết kế Kiến trúc AWS:**
    * Nắm chắc các quy tắc biểu diễn sơ đồ hệ thống điện toán đám mây chuẩn chuyên nghiệp, phân định rõ ràng các ranh giới không gian (Region, AZ, VPC, Public/Private Subnet) và luồng dữ liệu (Data Flow).
    * Sử dụng thành thạo bộ icon chính thức AWS Architecture Icons trên công cụ Draw.io/Lucidchart.
    * Tự tay vẽ hoàn chỉnh bản sơ đồ kiến trúc hệ thống thực tế chuẩn AWS gồm: *"User -> CloudFront (Edge Location) -> Route 53 -> ALB (Public Subnet) -> EC2 Auto Scaling (Private Subnet) + S3 (Static Content)"*.
* **Triển khai Backend Project:**
    * Triển khai thành công API `GET /api/products` hỗ trợ phân trang (limit, offset) và bộ lọc đa tiêu chí theo query params (`category`, `brand`, `scent`, `min_price`).
    * Triển khai thành công API `GET /api/products/{id}` (lấy thông tin chi tiết sản phẩm kèm các note hương) và API `DELETE /api/products/{id}` (xóa sản phẩm dành cho Admin).
    * Triển khai API `GET /api/search` hỗ trợ tìm kiếm sản phẩm theo tên (`?q=name`) và tối ưu hóa hiệu năng câu truy vấn danh sách trong Prisma ORM.
    * Xây dựng bộ test case kiểm thử toàn bộ các bộ lọc, phân trang và hoàn thành kiểm thử thành công toàn bộ Module Product Management trên Postman.
    * Hoàn tất thiết kế Prisma Schema chi tiết cho Module Giỏ hàng (Cart, CartItem) và Module Đơn hàng (Order, OrderItem).