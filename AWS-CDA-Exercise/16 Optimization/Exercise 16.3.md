#Exercise 16.3
##Create an AWS Config rule
In this exercise, using the AWS Management Console, you will create an AWS Config rule   to monitor whether Elastic IP addresses are attached to Amazon EC2 instances.
1.	Create an Elastic IP address to be used as part of this exercise, but do not attach it to any Amazon EC2 instance. See the following for instructions:
*https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html#using-instance-addressing-eips-releasing*
2.	Open the AWS Config console at *https://console.aws.amazon.com/config/*.
3.	Choose **Get Started Now**.
4.	On the **Settings** page, for **Resource types to record**, select **All resources**.
5.	For **Amazon S3 Bucket**, select the Amazon S3 bucket to which AWS Config sends configuration history and configuration snapshot files.
6.	For **Amazon SNS Topic**, select whether AWS Config  streams  information  by  selecting  the **Stream configuration changes and notifications to an Amazon SNS topic**.
7.	For **Topic Name**, type a name for your SNS topic.
8.	For **Bucket Name**, type a name for your Amazon S3 bucket.
9.	For **AWS Config role**, choose the IAM role that grants AWS Config permission to record configuration information and send this information to Amazon S3 and Amazon SNS.
10.	Choose **Create AWS Config service-linked role**, and then **Next**.
11.	On the **AWS Config Role** page, in the search bar, enter **eip** to find a specific rule from the list.
12.	Select the **eip-attached** rule.
13.	Choose **Next** and then **Confirm**.
AWS Config will run this rule against your resources. The rule flags the unattached EIP as non-compliant.
14.	Delete the AWS Config rule.
15.	Release the Elastic IP address. See the following for instructions: *https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html#using-instance-addressing-eips-releasing*

From the AWS Config console, you used AWS Config to create a rule to determine whether an Elastic IP address is attached to an Amazon EC2 instance.
