---
title : "Project overview"
date : 2024-01-01 
weight : 1 
chapter : false
pre : " <b> 5.1. </b> "
---

#### Business problem

Many applications store reports, backups, logs, or exported data in Amazon S3. In a hybrid architecture, those applications may run both inside AWS and in an on-premises data center. If S3 traffic uses the public Internet, the system has a wider security exposure and is harder to control.

This project solves that problem by building a private access path to S3 for both cloud and simulated on-premises workloads.

#### Project objectives

+ Build private S3 access from an EC2 instance in a VPC using a Gateway VPC Endpoint.
+ Build private S3 access from a simulated on-premises network using an Interface VPC Endpoint and Route 53 Resolver.
+ Restrict access with IAM permissions and an S3 VPC endpoint policy.
+ Validate the design with CLI tests, DNS checks, endpoint status checks, and CloudWatch/SSM operational evidence.
+ Provide clean-up steps to avoid unnecessary AWS cost.

#### VPC endpoints

+ **VPC endpoints** are virtual devices. They are horizontally scaled, redundant, and highly available VPC components. They allow communication between your compute resources and AWS services without imposing availability risks.
+ Compute resources running in VPC can access  **Amazon S3**  using a Gateway endpoint. PrivateLink interface endpoints can be used by compute resources running in VPC or on-premises.

#### Architecture overview

In this project, you will use two VPCs.
+ **"VPC Cloud"** is for cloud resources such as a  **Gateway endpoint** and an EC2 instance to test with. 
+ **"VPC On-Prem"** simulates an on-premises environment such as a factory or corporate datacenter. An EC2 instance running strongSwan VPN software has been deployed in "VPC On-prem" and automatically configured to establish a Site-to-Site VPN tunnel with AWS Transit Gateway. This VPN simulates connectivity from an on-premises location to the AWS cloud. To minimize costs, only one VPN instance is provisioned to support this workshop. When planning VPN connectivity for your production workloads, AWS recommends using multiple VPN devices for high availability.

![overview](/images/5-Workshop/5.1-Workshop-overview/diagram1.png)

#### AWS services used

| Service | Purpose in this project |
| --- | --- |
| Amazon S3 | Private object storage target for the test workload |
| Amazon VPC | Network boundary for cloud and simulated on-premises environments |
| VPC Gateway Endpoint | Private S3 access from resources inside the cloud VPC |
| VPC Interface Endpoint / PrivateLink | Private S3 access from the simulated on-premises network |
| Amazon EC2 | Test clients and VPN simulation instance |
| AWS Systems Manager | Secure shell access without opening inbound SSH |
| AWS Transit Gateway and Site-to-Site VPN | Hybrid connectivity simulation |
| Route 53 Resolver | Private DNS resolution for S3 endpoint names |
| IAM | Permission control and least-privilege access |
| AWS CloudFormation | Repeatable infrastructure provisioning |
| Amazon CloudWatch | Operational logs and metrics review |

#### Success criteria

+ The cloud EC2 instance can list and read the target S3 bucket through the Gateway endpoint.
+ The simulated on-premises instance resolves S3 DNS to private endpoint addresses and can access S3 through the Interface endpoint.
+ Public S3 access paths are not required for the tested workloads.
+ Endpoint policy limits access to the intended bucket and actions.
+ CloudWatch and Systems Manager provide evidence for troubleshooting and validation.
