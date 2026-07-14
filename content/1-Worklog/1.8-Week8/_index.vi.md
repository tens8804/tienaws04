---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8: Cấu hình Budgets, S3, IAM Role và SES

* Thiết lập kiểm soát chi phí, object storage, quyền ứng dụng và email identity.
* Thời gian thực hiện: từ 08/06/2026 đến 12/06/2026.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Tạo AWS Budget và kiểm tra ngưỡng cảnh báo chi phí | 08/06/2026 | 12/06/2026 | [Mục 5.3.1](../../5-workshop/5.3-budget-s3-iam/5.3.1-budget/) |
| 3 | - Tạo bucket `techblog-uploads-ttv-2026`, bật Block Public Access và SSE-S3 | 08/06/2026 | 12/06/2026 | [Mục 5.3.2](../../5-workshop/5.3-budget-s3-iam/5.3.2-s3/) |
| 4 | - Tạo `techblog-ec2-role` và chuẩn bị quyền S3, CloudWatch, SES | 08/06/2026 | 12/06/2026 | [Mục 5.3.3](../../5-workshop/5.3-budget-s3-iam/5.3.3-iam-role/) |
| 5 | - Xác minh email identity Amazon SES và trạng thái Sandbox | 08/06/2026 | 12/06/2026 | [Mục 5.3.4](../../5-workshop/5.3-budget-s3-iam/5.3.4-ses/) |

### Kết quả đạt được tuần 8:

* Budgets, S3, IAM Role và SES được chuẩn bị đúng với kiến trúc TechBlog.
* Cập nhật minh chứng, ghi chú kỹ thuật và nội dung liên quan vào báo cáo thực tập.
