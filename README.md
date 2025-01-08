# AWS Cloud Cost Optimization - Identifying Stale Resources

## Identifying Stale EBS Snapshots

In this, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

### Description:

The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

## Prerequisites
- An AWS account with required permissions.
- Basic knowledge of AWS Lambda, AWS SDK, and AWS CLI.
---

## Steps for Cloud Cost Optimization
### 1. **Create a role with IAM policies**
- Go to the IAM (Identity and Access Management) service in the AWS Management Console.
- ![policy](https://github.com/user-attachments/assets/78884152-7ec0-4bff-8da8-f098447086f9)
- Choose the permissions by adding them to one or more IAM groups or attaching policies directly.
- Create the role by choosing policies
### 2. **Identify Cost-Saving Opportunities**
- **Analyze Usage**: Use AWS Cost Explorer to identify underutilized resources.
- **Enable Trusted Advisor**: Review Trusted Advisor’s cost optimization recommendations.

### 2. **Automate Resource Scheduling**

Use Lambda functions to start and stop resources based on schedules:
- **EC2 Instances**: Automate stopping instances during non-business hours.
- **RDS Instances**: Use a similar approach to stop RDS databases when not in use

### 3.**Set Up Monitoring with CloudWatch**
- Use AWS CloudWatch to track resource usage and costs.
- Create metrics and alarms for resource utilization, cost anomalies, or thresholds.

#### 4. **Create Lambda Functions**
Create Lambda functions to identify and delete unused resources:
- Detect unattached EBS volumes and delete them.
- Identify and release unused Elastic IPs.
- Schedule Lambda functions to stop unused EC2 instances during off-peak hours and restart them when required.

#### 5. **Automate Cost Reporting**
- Use Lambda to fetch cost data from AWS Cost Explorer or AWS Billing and Cost Management APIs.
- Generate and send cost reports to stakeholders via email (using Amazon SES) or Slack.

#### 6. **Set Up Cost Anomaly Detection**
- Use Cost Anomaly Detection in conjunction with Lambda to automatically act on unusual spikes in costs.
- It will send notifications or automatically stop the offending resources.

#### 7. **Evaluate and Iterate**
- Regularly review and update Lambda functions based on resource usage patterns.
- Utilize reports and feedback to refine optimization strategies.
  

  


