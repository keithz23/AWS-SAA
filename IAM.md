#1. IAM Policies Structure: Is a JSON document that defines permissions for AWS resources.
Consists of:
-Version: Policy language version (always include "2012-10-17").
-Id: Optional identifier for the policy.
-Statement: One or more individual statements defining permissions.
Statement consists of:
-SID: Optional identifier for the statement.
-Effect: Whether to Allow or Deny the permissions.
-Principal: Account/user/role to which this policy applied to.
-Action: List of action this policy allows or denies.
-Resource: List of resources to which the actions applied to.
-Condition: conditions for when the policy is in effect (optional).
##For example:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "ExampleStatement",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::123456789012:user/ExampleUser"
      },
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::example-bucket",
      "Condition": {
        "IpAddress": {
          "aws:SourceIp": "0:0/0"
        }
      }
    }
  ]
}
```

#2. IAM MFA (Multi-Factor Authentication)
Password Policy:
-Strong passwords (minimum length, complexity requirements).
-Setup passwords expiration and reuse prevention.
-Allow users to change their own passwords.
-Prevent passwords re-use.
MFA (Multi-Factor Authentication):
-Users have access to your account and can possibly change configuration and delete your resources in your AWS account.
-You want to protect your Root account and IAM users with privileged access.
MFA = password + authentication code from a physical device or mobile app.
Main benefit of MFA: if a passwords is stolen or hacked, the account is not compromised without the second factor.
#3. Access Management Options
-To access AWS, you have three options:
--AWS Management Console: web-based user interface for managing AWS services.(Password + MFA).
--AWS CLI (Command Line Interface): tool to manage AWS services from the command line.(Access Key ID + Secret Access Key).
--AWS SDK (Software Development Kits): libraries for various programming languages to interact with AWS services programmatically.(Access Key ID + Secret Access Key).
-Access Keys are generated through the AWS console.
-User manage their own access keys.
-Access Keys are secret, just like a password, should be kept secret.
-Access Key Id=~username
-Secret Access Key=~password
#4. IAM Roles
-To do so, we will assign permissions to AWS services with IAM Roles.
Common Roles:
-EC2 Instance roles.
-Lambda Function roles.
-Roles for Cloud Formation.
#5. IAM Security Tools
-IAM Credentials Report (account level): a report that lists all users in your account and the status of their credentials (passwords, access keys, MFA).
-IAM Access Advisor (user level): shows the services that a user has accessed and when they last accessed them. You can use this information to identify unused permissions and refine policies.
#6. IAM Guidelines and Best Practices
-Enable MFA for all users, especially privileged users.
-Don't use root account for everyday tasks.
-Follow the principle of least privilege: grant only the permissions necessary for users to perform their tasks.
-Regularly review and rotate access keys and passwords.
-Audit permissions using IAM Access Advisor and Credentials Report.
-Never share your credentials.
#8. IAM Summary
-Users: mapped to a physical user, has a password for AWS console.
-Groups: contains user only.
-Policies:JSON documents that define permissions for users or groups.
-Roles: assigned to AWS services to grant permissions.(like EC2, Lambda).
-Security: MFA + password policy.
-AWS CLI: manage your AWS credentials with Access Key ID + Secret Access Key.
-AWS SDK: manage your AWS credentials programmatically with Access Key ID + Secret Access Key.
-Audit: IAM Credentials Report + IAM Access Advisor.
