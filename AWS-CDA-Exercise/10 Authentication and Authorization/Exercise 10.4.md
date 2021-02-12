#Exercise 10.4
##Setting up Amazon Cognito
In this exercise, you will set up Amazon Cognito, which is the service that provides authentication, authorization, and user management for web and mobile applications.
The two main components of Amazon Cognito are user pools and identity pools. User pools is a user directory that provides sign-up and sign-in services. Identity pools are used to provide access to other AWS services.
You can use identity pools and user pools separately or together. In this exercise, you will set up a user pool.
1.	In the AWS Directory Services console navigation pane, under Security, Identity & Compliance, choose **Cognito** and then choose **Manage User Pools**.
2.	Provide a name for your user pool. Enter *admin-group*.
3.	Specify how a user signs in. In this example, select **user name**, and then choose
**Next step**.
4.	Retain the default settings and choose **Next step**.
You can set MFA as optional or required. After a user pool is configured, you cannot change the MFA setting. Amazon Cognito uses Amazon SNS to send SMS messages. If MFA is enabled, you must assign a role with the correct policy to send SMS messages.
5.	Retain the default settings and choose **Next step**.
6.	On the **Attributes** page, retain the default settings for email customization, and choose **Next step**.
7.	To manage the AWS infrastructure, apply tags. Enter the following information, and then choose **Next step**:
a.	In **Tag Key**, enter *user*
b.	In **Tag Value**, enter *admin-user*.
8.	Select **No** and choose **Next step**.
*Amazon Cognito* can detect and retain your user’s device. This step enables you to con- figure that capability. In this example, however, you will select **No**. Choose **Next step**.
9.	Retain the default settings and choose **Next step**.
You can configure how client applications gain access to the user pool. In this exer- cise, no access is granted.
10.	Retain the default settings and choose **Next step**.
You can configure AWS Lambda functions that can be triggered during the Amazon Cognito operation. For this exercise, you will not configure any Lambda functions.
11.	On the **Review** page, review your configurations, and choose **Create pool**. You have successfully created a user pool in Amazon Cognito.
