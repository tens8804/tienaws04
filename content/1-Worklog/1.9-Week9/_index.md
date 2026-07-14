---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives: Deploying RDS MySQL and EC2

* Create the private database, compute instance, and secure EC2-to-RDS path.
* Timeline: from 15/06/2026 to 19/06/2026.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| Mon | - Created private Single-AZ RDS MySQL `techblog-db` and database `techblog` | 15/06/2026 | 19/06/2026 | [Section 5.4.1](../../5-workshop/5.4-rds-mysql/5.4.1-create-rds/) |
| Tue | - Allowed RDS TCP `3306` only from the EC2 Security Group | 15/06/2026 | 19/06/2026 | [Section 5.4.2](../../5-workshop/5.4-rds-mysql/5.4.2-security-groups/) |
| Wed | - Exported local data to `techblog.sql` and prepared the RDS endpoint | 15/06/2026 | 19/06/2026 | [Section 5.4](../../5-workshop/5.4-rds-mysql/) |
| Thu | - Launched Amazon Linux 2023 EC2 with the IAM Role and installed Java 17 and MariaDB client | 15/06/2026 | 19/06/2026 | [Section 5.5](../../5-workshop/5.5-deploy-ec2/) |

### Week 9 Achievements:

* RDS MySQL, EC2, Security Groups, and migration data were ready for the application.
* Updated evidence, technical notes, and related content in the internship report.
