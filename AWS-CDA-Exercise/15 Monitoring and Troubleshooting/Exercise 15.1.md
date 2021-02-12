#Exercise 15.1
##Create an Amazon CloudWatch Alarm on an Amazon S3 bucket
It is common to monitor the storage usage of your Amazon S3 buckets and trigger noti- fications when there is a large increase in storage used. In this exercise, you will use the AWS CLI to configure an Amazon CloudWatch alarm to trigger a notification when more than 1 KB of data is uploaded to an Amazon S3 bucket.
If you need directions while completing this exercise, see “Using Amazon CloudWatch Alarms” here: *https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html*
1.	Create an Amazon S3 bucket in your AWS account. For instructions, see this page: *https://docs.aws.amazon.com/AmazonS3/latest/user-guide/create-bucket.html*
2.	Open the Amazon CloudWatch console at *https://console.aws.amazon.com/cloudwatch/*.
3.	Select Alarms ➢ Create *Alarm*.
4.	Choose Select Metric.
a.	Select the All Metrics tab.
b.	Expand AWS Namespaces.
c.	Select S3.
d.	Select Storage Metrics.
e.	Select a metric where BucketName matches the name of the Amazon  S3  bucket that you created and where Metric Name is *BucketSizeBytes*.
5.	Choose Select Metric.
6.	Under Alarm Details:
a.	For Name, enter **S3 Storage Alarm**.
b.	For the comparator, select >= (greater than or equal to).
c.	Set the value to 1000 for 1 KB.
7.	Under Actions:
a.	For Whenever This Alarm, select State Is ALARM.
b.	For Send Notification To, select New List.
c.	For Name, enter **My S3 Alarm List**.
d.	For Email List, enter your email address.
8.	Choose Create Alarm.
The alarm is created in your account. If you already have data in your Amazon S3 bucket, it is switched from *Insufficient Data to Alarm* state. Otherwise, try uploading several files to your bucket to monitor changes in alarm state.
To delete the alarm, follow these steps:
1.	Open the Amazon CloudWatch console at *https://console.aws.amazon.com/cloudwatch/*.
2.	Select Alarms.
3.	Select the alarm you want to delete.
4.	For Actions, select Delete.

In this exercise, you created an Amazon CloudWatch alarm to notify administrators when large files are uploaded to Amazon S3 buckets in your account.
