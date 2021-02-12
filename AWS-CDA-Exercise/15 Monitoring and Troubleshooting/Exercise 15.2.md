#Exercise 15.2
##enable an AWS CloudTrail Trail on an Amazon S3 bucket
1.	In this exercise, you will set up access logs to an Amazon S3 bucket in your account  to monitor activity.Create an Amazon S3 bucket in your AWS account.
For instructions on how to do so, see the following: *https://docs.aws.amazon.com/AmazonS3/latest/user-guide/* create-bucket.html
2.	Open the AWS CloudTrail console at *https://console.aws.amazon.com/cloudtrail/*.
3.	Select Create Trail.
4.	Set Trail name to s3_logs.
5.	Under Management Events, select None.
6.	Under Data Events, select Add S3 Bucket.
7.	For S3 bucket, enter your Amazon S3 bucket name.
8.	Under Storage Location, for Create A New S3 bucket, select Yes.
9.	For Name, enter a name for your Amazon S3 bucket.
10.	Choose Create.

In this exercise, you enabled AWS CloudTrail to record data events and store correspond- ing logs to an Amazon S3 bucket.
