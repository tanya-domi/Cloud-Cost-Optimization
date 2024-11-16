
Cloud Cost Optimization - Identifying Stale Resources in AWS .

Identifying Stale EBS Snapshots in AWS.
In this example, we will create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

Description of Project:
The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

Python Boto3 module  using Lambda function  delete stale EBS snapshot that are not attached to any active instances and have been in  stale state for a certain period (e.g., 7 days)

lambda Function are event driven in nature  and  we Intergated Cloudwatch with lambda funtion using EventBridge  to schedule and  trigger function to run at a particular time (e.g,every  7days at 6am) to check and delete stale EBS snapshots in AWS.

