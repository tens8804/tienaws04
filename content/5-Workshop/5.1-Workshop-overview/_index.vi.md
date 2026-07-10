---
title : "Tổng quan project"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### Bài toán thực tế

Nhiều ứng dụng lưu báo cáo, bản sao lưu, log hoặc dữ liệu export trên Amazon S3. Trong kiến trúc hybrid, ứng dụng có thể chạy cả trong AWS và trong trung tâm dữ liệu on-premises. Nếu lưu lượng truy cập S3 đi qua Internet công cộng, hệ thống có phạm vi rủi ro bảo mật lớn hơn và khó kiểm soát hơn.

Project này giải quyết bài toán đó bằng cách xây dựng đường truy cập riêng tư đến S3 cho cả workload trong cloud và mạng on-premises mô phỏng.

#### Mục tiêu project

+ Xây dựng truy cập S3 riêng tư từ EC2 instance trong VPC bằng Gateway VPC Endpoint.
+ Xây dựng truy cập S3 riêng tư từ mạng on-premises mô phỏng bằng Interface VPC Endpoint và Route 53 Resolver.
+ Giới hạn truy cập bằng IAM permission và S3 VPC endpoint policy.
+ Xác minh thiết kế bằng CLI test, kiểm tra DNS, kiểm tra trạng thái endpoint và bằng chứng vận hành từ CloudWatch/SSM.
+ Cung cấp bước dọn dẹp để tránh phát sinh chi phí AWS không cần thiết.

#### Giới thiệu về VPC Endpoint

+ Điểm cuối VPC (endpoint) là thiết bị ảo. Chúng là các thành phần VPC có thể mở rộng theo chiều ngang, dự phòng và có tính sẵn sàng cao. Chúng cho phép giao tiếp giữa tài nguyên điện toán của bạn và dịch vụ AWS mà không gây ra rủi ro về tính sẵn sàng.
+ Tài nguyên điện toán đang chạy trong VPC có thể truy cập Amazon S3 bằng cách sử dụng điểm cuối Gateway. Interface Endpoint  PrivateLink có thể được sử dụng bởi tài nguyên chạy trong VPC hoặc tại TTDL.

#### Tổng quan kiến trúc

Trong project này, bạn sẽ sử dụng hai VPC.
+ **"VPC Cloud"** dành cho các tài nguyên cloud như Gateway endpoint và EC2 instance để kiểm tra.
+ **"VPC On-Prem"** mô phỏng môi trường truyền thống như nhà máy hoặc trung tâm dữ liệu của công ty. Một EC2 Instance chạy phần mềm StrongSwan VPN đã được triển khai trong "VPC On-prem" và được cấu hình tự động để thiết lập đường hầm VPN Site-to-Site với AWS Transit Gateway. VPN này mô phỏng kết nối từ một vị trí tại TTDL (on-prem) với AWS cloud. Để giảm thiểu chi phí, chỉ một phiên bản VPN được cung cấp để hỗ trợ workshop này. Khi lập kế hoạch kết nối VPN cho production workloads của bạn, AWS khuyên bạn nên sử dụng nhiều thiết bị VPN để có tính sẵn sàng cao.

![overview](/images/5-Workshop/5.1-Workshop-overview/diagram1.png)

#### Dịch vụ AWS sử dụng

| Dịch vụ | Vai trò trong project |
| --- | --- |
| Amazon S3 | Đích lưu trữ object riêng tư cho workload kiểm thử |
| Amazon VPC | Ranh giới mạng cho môi trường cloud và on-premises mô phỏng |
| VPC Gateway Endpoint | Truy cập S3 riêng tư từ tài nguyên trong cloud VPC |
| VPC Interface Endpoint / PrivateLink | Truy cập S3 riêng tư từ mạng on-premises mô phỏng |
| Amazon EC2 | Client kiểm thử và instance mô phỏng VPN |
| AWS Systems Manager | Truy cập shell an toàn mà không cần mở inbound SSH |
| AWS Transit Gateway và Site-to-Site VPN | Mô phỏng kết nối hybrid |
| Route 53 Resolver | Phân giải DNS riêng tư cho endpoint S3 |
| IAM | Kiểm soát quyền và áp dụng least privilege |
| AWS CloudFormation | Triển khai hạ tầng có thể lặp lại |
| Amazon CloudWatch | Xem log và metric phục vụ vận hành |

#### Tiêu chí thành công

+ EC2 instance trong cloud có thể list và đọc target S3 bucket thông qua Gateway endpoint.
+ Instance on-premises mô phỏng phân giải DNS S3 về địa chỉ private endpoint và truy cập S3 qua Interface endpoint.
+ Workload kiểm thử không cần public S3 access path.
+ Endpoint policy giới hạn truy cập vào đúng bucket và action cần thiết.
+ CloudWatch và Systems Manager cung cấp bằng chứng để kiểm tra và xử lý lỗi.
