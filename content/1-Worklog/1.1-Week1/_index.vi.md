---
title: "Worklog Tuần 1"
date: 2024-06-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1:

* **Chuẩn bị:** Làm quen với môi trường làm việc tại FCAJ, nắm rõ quy định đơn vị thực tập, tạo tài khoản AWS và nhận 200$ credits đầu tiên.
* **Bảo mật & Quản lý truy cập:** Nắm vững khái niệm Điện toán đám mây, thiết lập bảo mật 2 lớp (MFA) cho tài khoản Root và làm chủ các khái niệm cốt lõi của AWS IAM (Users, Groups, Policies).
* **Hạ tầng toàn cầu & Máy chủ ảo:** Hiểu rõ cấu trúc Hạ tầng toàn cầu của AWS (Region, AZ, Edge Location) và thực hành triển khai máy chủ ảo Amazon EC2 theo mô hình High Availability (Độ sẵn sàng cao).
* **Project:** Lập nhóm thành công.

### Các công việc đã triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- |---------- | ------------ | --------------- | -------------- |
| 2   | - Làm quen với các thành viên FCAJ <br> - Tìm nhóm làm project <br> - Đọc và lưu ý các nội quy, quy định tại đơn vị thực tập | 01/06/2026   | 01/06/2026 | [Nội quy](<https://hcm-rules.awsfcaj.com/>) |
| 3   | - Đăng ký tài khoản AWS Free Tier <br> - Tìm hiểu và cài đặt, cấu hình AWS CLI <br> - Thực hiện 5 nhiệm vụ lấy 100$ credit | 02/06/2026 | 02/06/2026 | [- Tạo tài khoản](<https://000001.awsstudygroup.com/vi/3-chi%E1%BA%BFn-l%C6%B0%E1%BB%A3c-nh%E1%BA%ADn-%C4%91%E1%BB%A7-200-credit/>) <br> [- AWS CLI cho người mới bắt đầu](<https://youtu.be/PWAnY-w1SGQ?si=8aHlanGBwnEOXvP8>) <br> [- Hướng dẫn chi tiết 5 nhiệm vụ "kiếm tiền"](<https://000001.awsstudygroup.com/vi/4-h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-chi-ti%E1%BA%BFt-5-nhi%E1%BB%87m-v%E1%BB%A5-ki%E1%BA%BFm-ti%E1%BB%81n/>) |
| 4   | - Tìm hiểu Điện toán đám mây là gì & Lợi ích của Cloud <br> - Bật bảo mật 2 lớp (MFA) cho tài khoản Root | 03/06/2026 | 03/06/2026 | [- Giới thiệu về điện toán đám mây](<https://youtube.com/playlist?list=PLdwqw0JzwbG7GCKA9bzUHhtqfJba4sllb&si=hDtv67NJfp8fcnc4>) <br> [- Đăng ký tài khoản AWS](<https://000001.awsstudygroup.com/3-chi%E1%BA%BFn-l%C6%B0%E1%BB%A3c-nh%E1%BA%ADn-%C4%91%E1%BB%A7-200-credit/>) <br> [- MFA](<https://youtu.be/zmVIebov_9g?si=Z6k-jFc6_0pfUBrI>) |
| 5   | - Tìm hiểu khái niệm AWS IAM: <br>&emsp; + Users <br>&emsp; + Groups <br>&emsp; + Policies <br> - **Thực hành:** Tạo IAM User mới trên Console và cấp quyền truy cập | 04/06/2026 | 04/06/2026 | [- AWS IAM, Root User, IAM User](<https://000002.awsstudygroup.com/1-introduction/1.1-group-user/>) <br> [- AWS managed policy, Custom Policy, Inline Policy](<https://youtu.be/MoHswdLFXT0?si=dJdKuOXu83hlKT9_>) |
| 6   | - Tìm hiểu hạ tầng toàn cầu AWS: <br>&emsp; + Region <br>&emsp; + Availability Zone (AZ) <br>&emsp; + Edge Location <br>&emsp; + Mô hình High Availability <br> - Tìm hiểu về Elastic Compute Cloud (EC2) <br> - **Thực hành:** Thao tác chọn Region, kiểm tra AZ ID trên Console và khởi tạo 2 máy chủ EC2 rải rác trên các AZ khác nhau  | 05/06/2025 | 05/06/2025 | [- Hạ Tầng Toàn Cầu Của AWS](<https://youtu.be/pjr5a-HYAjI?si=lCrafQYSOcyvnnHQ>) <br> [- Giới thiệu về Amazon EC2](<https://youtu.be/6PqZVGoeEEA?si=4lstPH2xk2FqYjJ2>) |


### Kết quả đạt được tuần 1:

* Đã kết nối với các thành viên và nắm chắc các quy định khi thực tập tại FCAJ.
* **Tài khoản AWS & Bảo mật:**
  * Khởi tạo thành công tài khoản AWS Free Tier và nhận đủ $100 credit qua 5 nhiệm vụ.
  * Bật thành công bảo mật 2 lớp (MFA) cho Root Account nhằm đảm bảo an toàn tài khoản.
* **AWS IAM:** 
  * Phân biệt được Root User và IAM User. 
  * Hiểu rõ cơ chế phân quyền qua AWS Managed/Custom/Inline Policies. 
  * Thực hành tạo thành công IAM User mới trên AWS Management Console và gán quyền hạn phù hợp.
* **Hạ tầng AWS & EC2:**
  * Hiểu rõ vai trò của Region, AZ, Edge Location và nguyên lý thiết kế hệ thống chịu lỗi High Availability.
  * Thực hành chọn Region, xác định AZ ID và khởi tạo thành công 2 instance EC2 nằm trên 2 AZ độc lập.
* **Project:** Đã tìm được nhóm làm project chung. 