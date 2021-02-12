#Exercise 5.2
##Create and Disable an AWS Key Management Service (AWS KMS) Key
In this exercise, you will create a customer master key (CMK) in the AWS Management
Console and then disable it. You can disable and re-enable the AWS KMS CMKs that
you manage.

1. Sign in to the AWS Management Console and open the AWS Key Management Service (AWS KMS) console at https://console.aws.amazon.com/kms.

2. Choose **Create key**.

3. Provide values for the key alias, description, and tag(s), and then choose **Next**.
The alias name cannot begin with aws. The aws prefix is reserved by AWS to represent AWS managed CMKs in your account.

4. Select one or more IAM users who can administer the CMK and then choose **Next**.
Make sure to select your IAM user.

5. Select one or more IAM users to use the CMK for cryptographic operations.
Make sure to select your IAM user

6. Choose **Finish** to create the CMK.

7. Locate the key in the AWS KMS console.

8. Select the check box next to the alias of the CMK that you want to disable.

9. Choose Key **actions ➢ Disable**.

If you disable a CMK, you cannot use it to encrypt or decrypt data until you re-enable it.
