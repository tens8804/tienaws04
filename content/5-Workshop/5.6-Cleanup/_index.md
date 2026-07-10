---
title : "Clean up"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---
Congratulations on completing this project!
In this workshop, you validated architecture patterns for accessing Amazon S3 without using the public Internet.
+ By creating a gateway endpoint, you enabled direct communication between EC2 resources and Amazon S3, without traversing an Internet Gateway. 
+ By creating an interface endpoint you extended S3 connectivity to resources running in your on-premises data center via AWS Site-to-Site VPN or Direct Connect. 

#### Validation summary

+ Cloud workload access was validated through the S3 Gateway endpoint.
+ Simulated on-premises access was validated through the S3 Interface endpoint and private DNS path.
+ Endpoint policy was used to restrict access scope.
+ CloudWatch/SSM evidence can be used to review sessions, logs, and troubleshooting signals.

#### Cost and security notes

+ Delete unused stacks, endpoints, EC2 instances, VPN resources, and S3 buckets immediately after testing.
+ Do not keep broad IAM permissions attached after the workshop.
+ Keep S3 Block Public Access enabled unless there is a documented exception.
+ In production, use redundant VPN devices or Direct Connect for higher availability.

#### clean up
1. Navigate to Hosted Zones on the left side of Route 53 console. Click the name of *s3.us-east-1.amazonaws.com* zone. Click Delete and confirm deletion by typing delete. 

![hosted zone](/images/5-Workshop/5.6-Cleanup/delete-zone.png)

2. Disassociate the Route 53 Resolver Rule `myS3Rule` from "VPC Onprem" and delete it.

![hosted zone](/images/5-Workshop/5.6-Cleanup/vpc.png)

4. Open the CloudFormation console  and delete the two CloudFormation Stacks that you created for this lab:
+ PLOnpremSetup
+ PLCloudSetup

![delete stack](/images/5-Workshop/5.6-Cleanup/delete-stack.png)

5. Delete S3 buckets
+ Open S3 console
+ Choose the bucket we created for the lab, click and confirm empty. Click delete and confirm delete.

![delete s3](/images/5-Workshop/5.6-Cleanup/delete-s3.png)

#### Personal reflection

The most important lesson from this project is that private connectivity is not only a networking task. It also requires DNS design, IAM policy control, route-table validation, monitoring evidence, and clean-up discipline. A future improvement would be to convert the manual steps into an IaC pipeline and add CloudWatch alarms for endpoint or VPN availability.
