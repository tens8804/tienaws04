---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---
# Secure Hybrid Access to S3 Using VPC Endpoints

#### Overview

This personal technical project designs and validates a secure hybrid access pattern for Amazon S3. The goal is to let workloads in an AWS VPC and a simulated on-premises network access S3 privately, without routing storage traffic through the public Internet.

The project is built as an end-to-end workshop with architecture explanation, hands-on deployment steps, validation, security controls, cost notes, and clean-up instructions. It uses more than three AWS services, including Amazon S3, Amazon VPC, VPC Endpoints, Amazon EC2, AWS Systems Manager, AWS Transit Gateway, AWS Site-to-Site VPN, Route 53 Resolver, IAM, CloudFormation, and CloudWatch.

Two S3 access patterns are implemented and compared:
+ **Gateway endpoint** - Routes S3 traffic from resources inside the VPC through a private route-table target.
+ **Interface endpoint** - Extends private S3 access to the simulated on-premises network through PrivateLink DNS resolution.

#### Project requirements mapping

+ **Real AWS use-case:** private storage access for hybrid workloads.
+ **Architecture:** two VPCs, S3 endpoints, VPN simulation, DNS forwarding, endpoint policy, and test instances.
+ **Implementation:** CloudFormation provisioning plus manual verification steps.
+ **Testing and measurement:** S3 access tests, DNS checks, Systems Manager sessions, VPC endpoint status, CloudWatch logs/metrics review, and expected results.
+ **Optimization:** least-privilege IAM, endpoint policy restriction, private routing, cost-aware clean-up, and removal of unused resources.
+ **Personal contribution:** endpoint policy hardening, validation checklist, and reflection on production improvements.

#### Content

1. [Workshop overview](5.1-Workshop-overview)
2. [Prerequisite](5.2-Prerequiste/)
3. [Access S3 from VPC](5.3-S3-vpc/)
4. [Access S3 from On-premises](5.4-S3-onprem/)
5. [VPC Endpoint Policies (Bonus)](5.5-Policy/)
6. [Clean up](5.6-Cleanup/)
