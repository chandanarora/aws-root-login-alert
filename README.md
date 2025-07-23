# 🚨 AWS Root Account Login Alert Project

This project sets up a real-time alert system to detect **Root Account login activity** in AWS. Since root account access is highly sensitive and should be rare, receiving notifications when it happens is essential for cloud security and compliance.

---

## 🧠 What I Did (7 Steps)

✅ Logged in with the AWS Root Account (⚠️ only for this test)  
✅ Performed a sensitive action (e.g., viewed billing dashboard)  
✅ Verified CloudTrail was enabled to record all activity  
✅ Created a **CloudTrail Trail** to log activity to an S3 bucket  
✅ Set up an **SNS Topic** and subscribed my email  
✅ Created a **CloudWatch Event Rule** to detect Root account logins  
✅ Successfully tested by logging in again as root and receiving an alert

---

## 🧱 Architecture Overview

[AWS Root Login]
↓
[CloudTrail Logs]
↓
[CloudWatch Event Rule]
↓
[SNS Topic]
↓
[Email Notification]


---

## 📁 S3 Bucket for CloudTrail Logs

- **Bucket Name**: `root-activity-trail-logs-chandan`
- Logs stored with prefix structure:

AWSLogs/{AccountID}/CloudTrail/{Region}/

- CloudTrail automatically delivers logs to this bucket

---

## 🔔 SNS Topic Setup

- **Topic Name**: `RootAccountAlertTopic`
- **Protocol**: Email
- **Subscription**: My email (confirmed via verification link)

---

## ⏰ CloudWatch Event Rule

- **Event Source**: `aws.signin`  
- **Detail Type**: `AWS Console Sign In via CloudTrail`  
- **Trigger Condition**:
```json
{
"detail": {
  "userIdentity": {
    "type": ["Root"]
  }
}
}

Target: SNS Topic (RootAccountAlertTopic)

✉️ Sample Email Notification
You’ll receive an email with log details when the root user signs in:

Event Name: ConsoleLogin

User Type: Root

Time: 2025-07-23T02:40:06Z

Source IP: 72.21.196.67

Region: us-east-1

User Agent: Chrome/138.0.0.0

ConsoleLogin: Success

📸 Screenshots Included
Billing dashboard access using root

CloudTrail logging to S3

SNS topic and subscription

CloudWatch rule for root activity

Email notification received

⚠️ Why This Matters
Logging and alerting on root account activity is a best practice:

🛡️ Prevents unauthorized access or misuse

📋 Helps with compliance (e.g., SOC 2, ISO 27001)

🚨 Detects risky behavior early

✅ What’s Next?
Enable log file validation and encryption (optional)

Create alerts for MFA disablement

Extend to monitor IAM policy changes or privilege escalations

📚 Learn More
AWS CloudTrail

Amazon SNS

Amazon CloudWatch Events
