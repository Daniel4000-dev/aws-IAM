# Exploring the users and groups and inspecting policies

## Business Scenario
I will be working with these users and groups to enable permissions that support the following business scenario.

My company is growing its use of AWS services and is using many Amazon EC2 instances and Amazon S3 buckets. I want to give access to new staff based on their job function, as indicated in the following table:

| User    | In Group      | Permissions                                   |
|---------|---------------|-----------------------------------------------|
| user-1  | S3-Support    | Read-only access to Amazon S3                |
| user-2  | EC2-Support   | Read-only access to Amazon EC2               |
| user-3  | EC2-Admin     | View, Start, and Stop Amazon EC2 instances   |


Note: The Region i am in is us-east-1 (N.Virginia)

### Steps
- Choose the service menu, locate the **Security**, **Identity** & **Compliance** services and choose **IAM***.
- In the navigation pane on the left, choose **Users**.
   I have the following users created;
   - user-1
   - user-2
   - user-3
- Choose the name of user-1.
  - This brings me to a summary page for user-1. The **Permissions** tab is displayed.
  - Note: user-1 is without any permissions, and also not a member of any groups.
- Choose the **Security Credentials** tab.
 - Notice that user-1 is assigned a **Console password**. This allows the user to access the AWS Management Console.
 - In the navigation pane on the left choose **User groups**.
   The following groups had been pre-created.
   - EC2-Admin
   - EC2-support
   - S3-support
- Choose the **EC2-support** group (this brings me to its summary page)
- Choose the **Permissions** tab.
  - This group has a managed policy called **AmazonEC2ReadOnlyAccess** associated with it.
  - Managed policies are pre-built polices (built by either AWS or Administrators) that can be attached to IAM users and groups.
  - When the policy is updated, the changes reflect accross all users and groups attached to the policy.
- Below policy name, choose the **AmazonEC2ReadOnlyAccess** policy.
- Choose the **JSON** tab.
  - A policy defines which actions are allowed or denied for specific AWS resources. This policy is granting permission to List and Describe (view) information about Amazon Elastic Compute Cloud (Amazon EC2), Elastic Load Balancing, Amazon CloudWatch, and Amazon EC2 Auto Scaling. This ability to view resources, but not modify them, is ideal for assigning to a support role.
  - Statements in an IAM policy have the following basic structure:
    - **Effect** says whether to Allow or Deny the permissions.
    - **Action** specifies the API calls that can be made against an AWS service (for example, cloudwatch:ListMetrics).
    - **Resource** defines the scope of entities covered by the policy rule (for example, a specific Amazon Simple Storage Service [Amazon S3] bucket or Amazon EC2 instance; an asterisk [ * ] means any resource).

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ec2:Describe*",
                "ec2:GetSecurityGroupsForVpc"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": "elasticloadbalancing:Describe*",
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "cloudwatch:ListMetrics",
                "cloudwatch:GetMetricStatistics",
                "cloudwatch:Describe*"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": "autoscaling:Describe*",
            "Resource": "*"
        }
    ]
}
```
-