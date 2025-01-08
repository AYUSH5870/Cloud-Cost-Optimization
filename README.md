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

### 1. **Identify Cost-Saving Opportunities**
- **Analyze Usage**: Use AWS Cost Explorer to identify underutilized resources.
- **Enable Trusted Advisor**: Review Trusted Advisor’s cost optimization recommendations.

---

### 2. **Automate Resource Scheduling**
Use Lambda functions to start and stop resources based on schedules:
- **EC2 Instances**: Automate stopping instances during non-business hours.
- **RDS Instances**: Use a similar approach to stop RDS databases when not in use.
  


