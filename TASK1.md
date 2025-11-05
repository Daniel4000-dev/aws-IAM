# Exploring the users and groups and inspecting policies

## Business Scenario
I will be working with these users and groups to enable permissions that support the following business scenario.

My company is growing its use of AWS services and is using many Amazon EC2 instances and Amazon S3 buckets. I want to give access to new staff based on their job function, as indicated in the following table:

| User    | In Group      | Permissions                                   |
|---------|---------------|-----------------------------------------------|
| user-1  | S3-Support    | Read-only access to Amazon S3                |
| user-2  | EC2-Support   | Read-only access to Amazon EC2               |
| user-3  | EC2-Admin     | View, Start, and Stop Amazon EC2 instances   |
