---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11: Kiểm thử, monitoring, rà soát bảo mật và lập kế hoạch cleanup

* Kiểm thử end-to-end, bổ sung giám sát vận hành, rà soát bảo mật và chuẩn bị cleanup.
* Thời gian thực hiện: từ 29/06/2026 đến 03/07/2026.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Kiểm thử chức năng theo role, vòng đời ảnh S3, lỗi HTTP 413 và thông báo đăng ký SES | 29/06/2026 | 03/07/2026 | [Mục 5.6](../../5-workshop/5.6-testing-operations/) |
| 3 | - Kiểm tra systemd/application log và cấu hình CloudWatch Agent cho `/techblog/application` | 29/06/2026 | 03/07/2026 | [Mục 5.6](../../5-workshop/5.6-testing-operations/) |
| 4 | - Tạo `techblog-high-cpu`, rà soát EC2, RDS, S3, IAM, SES và secrets | 29/06/2026 | 03/07/2026 | [Mục 5.6](../../5-workshop/5.6-testing-operations/) |
| 5 | - Ghi lại thứ tự cleanup EC2/EBS, RDS, S3, CloudWatch, SES, IAM và Security Group | 29/06/2026 | 03/07/2026 | [Mục 5.7](../../5-workshop/5.7-cleanup/) |

### Kết quả đạt được tuần 11:

* Hoàn thành bằng chứng kiểm thử, CloudWatch Logs/alarm, security review và checklist cleanup.
* Cập nhật minh chứng, ghi chú kỹ thuật và nội dung liên quan vào báo cáo thực tập.
