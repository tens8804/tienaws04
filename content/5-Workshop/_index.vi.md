---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Đảm bảo truy cập hybrid an toàn đến S3 bằng VPC Endpoint

#### Tổng quan

Dự án kỹ thuật cá nhân này thiết kế và kiểm thử mô hình truy cập Amazon S3 an toàn cho môi trường hybrid. Mục tiêu là cho phép workload trong AWS VPC và mạng on-premises mô phỏng truy cập S3 bằng đường truyền riêng tư, không đưa lưu lượng lưu trữ ra Internet công cộng.

Báo cáo được trình bày như một workshop end-to-end, có mô tả kiến trúc, các bước triển khai, kiểm thử, kiểm soát bảo mật, ghi chú chi phí và dọn dẹp tài nguyên. Project sử dụng hơn ba dịch vụ AWS, gồm Amazon S3, Amazon VPC, VPC Endpoint, Amazon EC2, AWS Systems Manager, AWS Transit Gateway, AWS Site-to-Site VPN, Route 53 Resolver, IAM, CloudFormation và CloudWatch.

Hai mô hình truy cập S3 được triển khai và so sánh:
+ **Gateway endpoint** - Định tuyến lưu lượng S3 từ tài nguyên trong VPC thông qua route table riêng tư.
+ **Interface endpoint** - Mở rộng truy cập S3 riêng tư cho mạng on-premises mô phỏng thông qua PrivateLink và DNS resolution.

#### Đối chiếu yêu cầu project

+ **Use-case AWS thực tế:** truy cập storage riêng tư cho workload hybrid.
+ **Kiến trúc:** hai VPC, S3 endpoint, VPN mô phỏng, DNS forwarding, endpoint policy và instance kiểm thử.
+ **Triển khai:** dùng CloudFormation để khởi tạo môi trường và có các bước xác minh thủ công.
+ **Kiểm thử và đo lường:** kiểm thử truy cập S3, kiểm tra DNS, phiên Systems Manager, trạng thái VPC endpoint, log/metric CloudWatch và kết quả mong đợi.
+ **Tối ưu:** IAM theo least privilege, giới hạn bằng endpoint policy, định tuyến riêng tư, kiểm soát chi phí và dọn dẹp tài nguyên.
+ **Đóng góp cá nhân:** bổ sung hardening endpoint policy, checklist kiểm thử và nhận xét hướng cải thiện production.

#### Nội dung

1. [Tổng quan về workshop](5.1-Workshop-overview/)
2. [Chuẩn bị](5.2-Prerequiste/)
3. [Truy cập đến S3 từ VPC](5.3-S3-vpc/)
4. [Truy cập đến S3 từ TTDL On-premises](5.4-S3-onprem/)
5. [VPC Endpoint Policies (làm thêm)](5.5-Policy/)
6. [Dọn dẹp tài nguyên](5.6-Cleanup/)
