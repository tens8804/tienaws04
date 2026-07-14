---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9: Triển khai RDS MySQL và EC2

* Tạo database private, compute instance và đường kết nối bảo mật giữa EC2 với RDS.
* Thời gian thực hiện: từ 15/06/2026 đến 19/06/2026.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Tạo RDS MySQL `techblog-db` private, Single-AZ và cấu hình database `techblog` | 15/06/2026 | 19/06/2026 | [Mục 5.4.1](../../5-workshop/5.4-rds-mysql/5.4.1-create-rds/) |
| 3 | - Cấu hình Security Group để RDS chỉ nhận TCP `3306` từ EC2 Security Group | 15/06/2026 | 19/06/2026 | [Mục 5.4.2](../../5-workshop/5.4-rds-mysql/5.4.2-security-groups/) |
| 4 | - Export dữ liệu local thành `techblog.sql` và chuẩn bị RDS endpoint | 15/06/2026 | 19/06/2026 | [Mục 5.4](../../5-workshop/5.4-rds-mysql/) |
| 5 | - Tạo EC2 Amazon Linux 2023, gắn IAM Role và cài Java 17, MariaDB client | 15/06/2026 | 19/06/2026 | [Mục 5.5](../../5-workshop/5.5-deploy-ec2/) |

### Kết quả đạt được tuần 9:

* RDS MySQL, EC2, Security Group và dữ liệu migration đã sẵn sàng cho ứng dụng.
* Cập nhật minh chứng, ghi chú kỹ thuật và nội dung liên quan vào báo cáo thực tập.
