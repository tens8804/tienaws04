---
title : "Dọn dẹp tài nguyên"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

#### Dọn dẹp tài nguyên

Xin chúc mừng bạn đã hoàn thành project này!
Trong workshop này, bạn đã kiểm thử các mô hình kiến trúc để truy cập Amazon S3 mà không sử dụng Internet công cộng.

+ Bằng cách tạo Gateway endpoint, bạn đã cho phép giao tiếp trực tiếp giữa EC2 và Amazon S3 mà không đi qua Internet Gateway.
+ Bằng cách tạo Interface endpoint, bạn đã mở rộng kết nối S3 đến các tài nguyên chạy trong trung tâm dữ liệu on-premises thông qua AWS Site-to-Site VPN hoặc Direct Connect.

#### Tổng kết kiểm thử

+ Workload trong cloud đã được kiểm thử truy cập S3 thông qua Gateway endpoint.
+ Mạng on-premises mô phỏng đã được kiểm thử truy cập S3 thông qua Interface endpoint và luồng DNS riêng tư.
+ Endpoint policy được dùng để giới hạn phạm vi truy cập.
+ CloudWatch/SSM cung cấp bằng chứng để xem session, log và tín hiệu xử lý lỗi.

#### Ghi chú chi phí và bảo mật

+ Xóa stack, endpoint, EC2 instance, VPN resource và S3 bucket không còn dùng ngay sau khi kiểm thử.
+ Không giữ IAM permission quá rộng sau khi hoàn thành workshop.
+ Giữ S3 Block Public Access ở trạng thái bật nếu không có ngoại lệ được ghi nhận rõ ràng.
+ Trong production, nên dùng nhiều VPN device hoặc Direct Connect để tăng tính sẵn sàng.

#### Dọn dẹp
1. Điều hướng đến Hosted Zones trên phía trái của bảng điều khiển Route 53. Nhấp vào tên của  s3.us-east-1.amazonaws.com zone. Nhấp vào Delete và xác nhận việc xóa bằng cách nhập từ khóa "delete".

![hosted zone](/images/5-Workshop/5.6-Cleanup/delete-zone.png)

2. Gỡ liên kết Route 53 Resolver Rule `myS3Rule` khỏi "VPC Onprem" và xóa rule này.

![hosted zone](/images/5-Workshop/5.6-Cleanup/vpc.png)

4. Mở console của CloudFormation và xóa hai stack CloudFormation mà bạn đã tạo cho bài thực hành này:
+ PLOnpremSetup
+ PLCloudSetup

![delete stack](/images/5-Workshop/5.6-Cleanup/delete-stack.png)

5. Xóa các S3 bucket

+ Mở bảng điều khiển S3
+ Chọn bucket đã tạo cho lab, xác nhận empty bucket, sau đó chọn Delete và xác nhận xóa.

![delete s3](/images/5-Workshop/5.6-Cleanup/delete-s3.png)

#### Nhận xét cá nhân

Bài học quan trọng nhất từ project này là private connectivity không chỉ là bài toán network. Thiết kế cần kết hợp DNS, IAM policy, kiểm tra route table, bằng chứng monitoring và kỷ luật dọn dẹp tài nguyên. Hướng phát triển tiếp theo là chuyển các bước thủ công thành IaC pipeline và bổ sung CloudWatch alarm cho trạng thái endpoint hoặc VPN.
