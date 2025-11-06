# Signing in and testing user permissions
here I test the permissions inherited by IAM users in the console.

## 3.1: Get the console sign-in URL
- In the navigation pane on the left, choose Dashboard.
  - Notice the Sign-in URL for IAM users in this account section at the top of the page. The sign-in URL looks similar to the following: **https://123456789012.signin.aws.amazon.com/console**.
  - This link can be used to sign in to the AWS account that I am currently using.
- Copied the sign-in link to a text editor.

## 3.2: Test user-1 permissions
- Opened a private or incognito window in my browser.
- Pasted the sign-in link into the private browser, and pressed ENTER.
  - I will now sign-in as user-1, who was hired as my Amazon S3 storage support staff.
- Signed in with the following credentials:
  - **IAM user name**: user-1.
  - **Password**: ```Lab-Password1```
- Choose the **Services menu**, and choose **S3**. Or use the search bar to find and choose **S3**.
- Choose the name of one of my buckets, and browse the contents.
  - Because this user is part of the S3-Support group in IAM, they have permissions to view a list of Amazon S3 buckets and their contents. Now, to test whether the user has access to Amazon EC2.
- Choose the **Services menu**, and choose **EC2**. I can also use the search bar to find and choose **EC2**.
- In the left navigation pane, choose **Instances**.
  - I cannot see any instances. Instead, an error message says I are not authorized to perform this operation. This user has not been assigned any permissions to use Amazon EC2.
  - I will now sign in as user-2, who was hired as your Amazon EC2 support person.
- First, sign out user-1 from the console.
  - In the upper-right corner of the page, choose **user-1**.
  - Choose **Sign Out**.

  ## 3.3: Test user-2 permissions
  - Pasted the sign-in link into the private browser again, and press ENTER.
  - Signed in with the following credentials: