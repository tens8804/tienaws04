---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10: Triển khai TechBlog và cấu hình tích hợp AWS

* Đưa TechBlog lên EC2, kết nối các dịch vụ AWS và vận hành ổn định bằng systemd.
* Thời gian thực hiện: từ 22/06/2026 đến 26/06/2026.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Kết nối EC2 đến RDS, import `techblog.sql` và xác minh chín bảng dữ liệu | 22/06/2026 | 26/06/2026 | [Mục 5.5.3](../../5-workshop/5.5-deploy-ec2/5.5.3-rds-import/) |
| 3 | - Build và upload JAR TechBlog lên EC2 | 22/06/2026 | 26/06/2026 | [Mục 5.5.4](../../5-workshop/5.5-deploy-ec2/5.5.4-build-upload-jar/) |
| 4 | - Cấu hình RDS, S3, SES, log và Region trong `/etc/techblog/techblog.env` | 22/06/2026 | 26/06/2026 | [Mục 5.5.5](../../5-workshop/5.5-deploy-ec2/5.5.5-runtime-integration/) |
| 5 | - Tạo `techblog.service`, khởi động bằng systemd và xác minh HTTP 200 trên port `8080` | 22/06/2026 | 26/06/2026 | [Mục 5.5.6](../../5-workshop/5.5-deploy-ec2/5.5.6-systemd/) |

### Kết quả đạt được tuần 10:

* TechBlog chạy bằng `techblog.service`, kết nối RDS, S3 và SES, trả HTTP 200 trên port `8080`.
* Cập nhật minh chứng, ghi chú kỹ thuật và nội dung liên quan vào báo cáo thực tập.
