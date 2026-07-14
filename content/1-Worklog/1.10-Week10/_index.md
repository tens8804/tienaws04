---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives: Deploying TechBlog and configuring AWS integrations

* Deploy TechBlog to EC2, connect its AWS services, and operate it reliably with systemd.
* Timeline: from 22/06/2026 to 26/06/2026.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| Mon | - Connected EC2 to RDS, imported `techblog.sql`, and verified nine tables | 22/06/2026 | 26/06/2026 | [Section 5.5.3](../../5-workshop/5.5-deploy-ec2/5.5.3-rds-import/) |
| Tue | - Built and uploaded the TechBlog executable JAR to EC2 | 22/06/2026 | 26/06/2026 | [Section 5.5.4](../../5-workshop/5.5-deploy-ec2/5.5.4-build-upload-jar/) |
| Wed | - Configured RDS, S3, SES, logging, and Region values in `/etc/techblog/techblog.env` | 22/06/2026 | 26/06/2026 | [Section 5.5.5](../../5-workshop/5.5-deploy-ec2/5.5.5-runtime-integration/) |
| Thu | - Created `techblog.service`, started systemd, and verified HTTP 200 on port `8080` | 22/06/2026 | 26/06/2026 | [Section 5.5.6](../../5-workshop/5.5-deploy-ec2/5.5.6-systemd/) |

### Week 10 Achievements:

* TechBlog ran as `techblog.service`, connected to RDS, S3, and SES, and returned HTTP 200 on port `8080`.
* Updated evidence, technical notes, and related content in the internship report.
