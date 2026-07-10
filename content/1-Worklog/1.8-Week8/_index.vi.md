---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8: Triển khai Gateway VPC Endpoint cho S3

* Thiết lập truy cập S3 private từ workload trong VPC Cloud.
* Thời gian thực hiện: từ 08/06/2026 đến 12/06/2026.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | - Tạo S3 bucket kiểm thử và đảm bảo bucket không public | 08/06/2026 | 12/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 3 | - Tạo Gateway VPC Endpoint cho S3 và liên kết với route table phù hợp | 08/06/2026 | 12/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - Truy cập EC2 bằng Session Manager và kiểm thử aws s3 ls/cp qua endpoint | 08/06/2026 | 12/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Chụp ảnh route table, endpoint status và kết quả CLI để đưa vào workshop | 08/06/2026 | 12/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 8:

* Xác minh EC2 trong VPC có thể truy cập S3 thông qua Gateway endpoint thay vì public Internet.
* Cập nhật minh chứng, ghi chú kỹ thuật và nội dung liên quan vào báo cáo thực tập.