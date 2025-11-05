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
 - Note: user-1 is without any permissions.
 - Note: user-1 is also not a member of any groups.
- Choose the **Security Credentials** tab.
 - Notice that user-1 is assigned a **Console password**. This allows the user to access the AWS Management Console.