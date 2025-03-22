<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Security Monitoring System

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-monitoring)

**Author:** Praneeth Bhandwalkar  
**Email:** praneeth2003bhandwalkar2.0@gmail.com

---

![Image](http://learn.nextwork.org/thankful_azure_innocent_oriental_melon/uploads/aws-security-monitoring_reghtjy)

---

## Introducing Today's Project!

In this project, I will demonstrate a project on setting up a monitoring system with AWS CloudTrail, CloudWatch, and SNS, I'm doing this project to learn about AWS CloudTrail and SNS because these services are new to me, and I'm excited to use them in the project.

### Tools and concepts

Services I used were AWS Secrets Manager, AWS CloudTrail, Amazon CloudWatch, Amazon SNS, Amazon S3, and AWS CLI. Key concepts I learned include secure secret management, monitoring, and automation.

### Project reflection

This project took me approximately two and a half hours to complete. The most challenging part was to receive an email. 

---

## Create a Secret

Secrets Manager is a service that securely manages and stores sensitive information like API keys and passwords. You could use Secrets Manager to automate secret rotation, enhance security, and manage access efficiently.

To set up my project, I created a secret called TopSecretInfo, which contains a secret message.

![Image](http://learn.nextwork.org/thankful_azure_innocent_oriental_melon/uploads/aws-security-monitoring_o5p6q7r8)

---

## Set Up CloudTrail

CloudTrail is an AWS service that records API calls and user activity within your AWS account, helping with auditing and compliance. I set up a trail to log specific events and deliver them to an S3 bucket for analysis.

CloudTrail events include types like Management Events, which track operations on AWS resources; Data Events, focusing on data request operations; and Insight Events, which identify unusual API activity patterns.

### Read vs Write Activity

Read API activity involves retrieving data from a system without altering it, acting as a means to access and explore information. Write API activity involves updating data within a system. For this project, we need both to esure data management and user interaction.

---

## Verifying CloudTrail

I retrieved the secret in two ways: First through visiting the Secret Manager and viewing it in Secret value Second by using AWS CloudShell with one command.

To analyze my CloudTrail events, I visited the CloudTrail Dashboard and visited the Event history I found so many event histories and searched for secretsmanager.amazonaws.com This tells me that secret's value was retrieved or used.

![Image](http://learn.nextwork.org/thankful_azure_innocent_oriental_melon/uploads/aws-security-monitoring_s8t9u0v1)

---

## CloudWatch Metrics

CloudWatch Logs is a monitoring service by AWS that collects and stores log files from various resources, enabling centralized log management. It's important for monitoring because it helps identify issues, analyze performance, and automate responses through real-time insights.

CloudTrail's Event History is useful for auditing and tracking API activity within an AWS account, ensuring compliance and security. While CloudWatch Logs are better for real-time monitoring and analyzing application performance.

A CloudWatch metric is a time-ordered set of data points that reflect the performance of AWS resources. When setting up a metric, the metric value represents the specific data point collected over time. Default value is used when no specific value is provided, ensuring that monitoring continues without interruption.

![Image](http://learn.nextwork.org/thankful_azure_innocent_oriental_melon/uploads/aws-security-monitoring_a9b0c1d2)

---

## CloudWatch Alarm

A CloudWatch alarm is a monitoring tool that triggers notifications based on specified metrics. I set my CloudWatch alarm threshold to a specific value, so the alarm will trigger when the monitored metric exceeds or falls below this threshold, indicating a potential issue.

I created an SNS topic along the way. An SNS topic is a communication channel in Amazon Simple Notification Service that allows messages to be sent to multiple subscribers. My SNS topic is set up to notify users of important updates.

AWS requires email confirmation because it ensures the subscriber genuinely wants notifications. This helps prevent unauthorized subscriptions and potential spam, enhancing security and user control.

![Image](http://learn.nextwork.org/thankful_azure_innocent_oriental_melon/uploads/aws-security-monitoring_fsdghstt)

---

## Troubleshooting Notification Errors

To test my monitoring system, I simulated various scenarios and tracked performance metrics. The results were promising, showing quick response times and accurate alerts for all monitored parameters.

When troubleshooting the notification issues, I checked:
CloudTrail Log Delivery to ensure logs were being sent correctly.
Metric Filter for monitoring specific log patterns.
Alarm Configuration to verify alerts were set up properly.
SNS Subscription to confirm notifications were correctly configured.
The results were effective in diagnosing the problem.

I initially didn't receive an email before because there were issues with the CloudTrail log delivery, often due to misconfigurations in the SNS subscriptions. The key solution was to verify and reconfigure the CloudTrail settings, ensuring proper alarm configuration and metric filters were in place.

---

## Success!

To validate my monitoring system, I checked its alerts against actual incidents. I received timely notifications "Secret is accessed" in US East (N. Virginia), confirming accuracy and responsiveness, and ensuring reliability in real scenarios.

![Image](http://learn.nextwork.org/thankful_azure_innocent_oriental_melon/uploads/aws-security-monitoring_ageraergearge)

---

## Comparing CloudWatch with CloudTrail Notifications

In a project extension, I updated my CloudTrail configurations because it was essential to enhance security monitoring and ensure direct CloudTrail SNS Notifications.

After enabling CloudTrail SNS notifications, my inbox received frequent alerts about AWS account activities. In terms of the usefulness of these emails, I thought they provided critical real-time updates.

![Image](http://learn.nextwork.org/thankful_azure_innocent_oriental_melon/uploads/aws-security-monitoring_d7e8f9g0)

---

---
