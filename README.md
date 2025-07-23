# 🔐 AWS Root Account Login Alert Project

This project demonstrates how to detect and alert on the use of the AWS root account — a critical security best practice.

---

## 🧪 What I Did

✅ Logged in using the root account (simulated sensitive action)  
✅ Accessed the AWS Billing Dashboard  
✅ Enabled **AWS CloudTrail** for account-wide logging  
✅ Created a **CloudTrail Trail** to log events to an S3 bucket  
✅ Created an **SNS Topic** and subscribed my email for alerts  
✅ Created a **CloudWatch EventBridge Rule** that detects RootAccountUsage  
✅ Verified the setup by logging in again and receiving an **email alert**  

---

## 📸 Screenshots Included

- Root login and billing access  
- CloudTrail setup and logging  
- SNS Topic + Email subscription  
- EventBridge Rule triggered  
- Email alert received

---

## 🛡️ Key Services Used

| Service     | Purpose                                  |
|-------------|------------------------------------------|
| CloudTrail  | Logs all management events               |
| S3          | Stores log files from CloudTrail         |
| SNS         | Sends notification to email              |
| EventBridge | Triggers alert on RootAccountUsage       |

---

## ⚠️ Why This Matters

Logging and alerting on root account activity is a best practice:

- 🛑 Prevents unauthorized access or misuse  
- ✅ Helps with compliance (e.g., SOC 2, ISO 27001)  
- 🔎 Detects risky behavior early  

---

## ✅ What’s Next?

- Add **log file validation** and **encryption** to your CloudTrail logs  
- Detect and alert on **MFA disablement**  
- Extend monitoring to **IAM policy changes** or **privilege escalations**  

---

## 📚 Learn More

- [AWS CloudTrail Documentation](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)  
- [Amazon SNS](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)  
- [Amazon EventBridge (CloudWatch Events)](https://docs.aws.amazon.com/eventbridge/latest/userguide/what-is-amazon-eventbridge.html)