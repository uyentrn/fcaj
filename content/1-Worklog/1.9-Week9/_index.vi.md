---
title: "Worklog Tuần 9"
date: 2026-07-27
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:
* **Nghiên cứu Quản lý Cấu hình Bảo mật & Tự động hóa Triển khai (CI/CD):** Nắm vững rủi ro lộ mã bảo mật (Secrets/API Keys), thực hành quản lý biến môi trường an toàn với AWS Systems Manager (SSM) Parameter Store (SecureString, AWS SDK), tìm hiểu quy trình CI/CD Pipeline và xây dựng Workflow tự động hóa build/deploy mã nguồn khi push Git.
* **Hoàn thiện Module Đánh giá (Reviews) & Tổng kết Báo cáo Thực tập:** Thiết kế Schema và triển khai trọn bộ API CRUD cho Module Reviews, đồng thời rà soát toàn bộ Worklog 9 tuần, tổng hợp tài liệu kỹ thuật và hoàn thiện báo cáo thực tập.

### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | ----------| ------------ | --------------- | -------------- |
| 2   | - Tìm hiểu rủi ro khi hardcode bí mật (Secrets/API Keys) trong nguồn mã nguồn <br> - Tìm hiểu dịch vụ AWS Systems Manager (SSM) Parameter Store <br> - **Project:** Thiết kế Prisma Schema cho Module Reviews (Review) và viết các API: <br>&emsp; + Viết API POST /api/products/{id}/reviews (gửi đánh giá/xếp hạng sản phẩm cho Client đã mua hàng) <br>&emsp; + Viết API GET /api/products/{id}/reviews (lấy tất cả đánh giá của một sản phẩm)| 27/07/2026 | 27/07/2026 | [AWS Parameter Store Overview](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-parameter-store.html) |
| 3   | - **Thực hành:** <br>&emsp; + Lưu trữ tham số (SecureString) trên Parameter Store <br>&emsp; + Truy xuất trực tiếp từ ứng dụng/Lambda bằng AWS SDK <br> - **Project:** <br>&emsp; + Viết API PUT /api/reviews/{id} (cập nhật review đã tạo cho Client) <br>&emsp; + Viết API DELETE /api/reviews/{id} (xóa đánh giá theo ID cho Client) <br>&emsp; + Viết API DELETE /api/admin/reviews/{id} (xóa đánh giá theo ID cho Admin)| 28/07/2026 | 28/07/2026 | [Creating Secure and Encrypted String Parameters](https://www.youtube.com/watch?v=cBIAjH_Sy-A) |
| 4   | - Tìm hiểu tổng quan về luồng CI/CD Pipeline (Build, Test, Deploy) trong các dự án phần mềm hiện đại | 29/07/2026 | 29/07/2026 | [The IDEAL & Practical CI / CD Pipeline](https://www.youtube.com/watch?v=OPwU3UWCxhw) |
| 5   | - **Thực hành:** <br>&emsp; + Thiết lập Workflow tự động với GitHub Actions (hoặc AWS CodePipeline) để build <br>&emsp; + Deploy mã nguồn lên S3/ AWS App Runner mỗi khi có thao tác `git push` | 30/07/2026 | 31/07/2026 | [Xây dựng CI/CD tự động bằng AWS CodePipeline, ECS, Fargate, CodeBuild, CodeDeploy, Github](https://www.youtube.com/watch?v=7L3vJlwOTnk) |
| 6 | - Kiểm tra và hoàn thiện báo cáo thực tập | 31/07/2026 | 31/07/2026 |  |

### Kết quả đạt được tuần 9:
* **Quản lý Cấu hình & Bảo mật Bí mật (Secrets Management):**
    * Thấu hiểu sâu sắc các rủi ro an ninh khi hardcode bí mật, mật khẩu hay API Keys trực tiếp trong mã nguồn.
    * Thao tác thành công với AWS Systems Manager (SSM) Parameter Store để quản lý và lưu trữ cấu hình, biến môi trường.
    * Thực hành lưu trữ tham số mã hóa (`SecureString`) và viết code sử dụng AWS SDK để truy xuất trực tiếp bí mật từ ứng dụng/Lambda một cách an toàn.
* **Tự động hóa Triển khai (CI/CD Pipeline):**
    * Nắm vững tư duy và quy trình chuẩn của một luồng CI/CD (Build, Test, Deploy) trong phát triển phần mềm hiện đại.
    * Xây dựng thành công Workflow tự động hóa bằng GitHub Actions (hoặc AWS CodePipeline), tự động kích hoạt quá trình build và deploy mã nguồn lên S3 / AWS App Runner mỗi khi thực hiện thao tác `git push`.
* **Triển khai Backend Project (Review Module) & Hoàn tất Báo cáo:**
    * Thiết kế hoàn chỉnh Prisma Schema cho Module Đánh giá (Review).
    * Triển khai bộ API cho Client: `POST /api/products/{id}/reviews` (gửi đánh giá/xếp hạng sản phẩm sau khi mua hàng), `GET /api/products/{id}/reviews` (xem danh sách đánh giá sản phẩm), `PUT /api/reviews/{id}` (chỉnh sửa đánh giá) và `DELETE /api/reviews/{id}` (xóa đánh giá của chính mình).
    * Triển khai API `DELETE /api/admin/reviews/{id}` cho Admin quản lý và kiểm duyệt các nội dung đánh giá không phù hợp.
    * Hoàn thiện trọn vẹn bộ hồ sơ thực tập gồm báo cáo tổng kết, tài liệu kỹ thuật của project và toàn bộ hệ thống Worklog 9 tuần.