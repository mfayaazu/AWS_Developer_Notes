#Exercise 14.8
##Enable Cross-region replication
In this exercise, you will enable cross-region replication of the contents of the original bucket to a new bucket in a different region.
1.	While signed into the AWS Management Console, open the Amazon S3 console at *https://console.aws.amazon.com/s3/*.
2.	Create a new bucket in a different region from the bucket that you created in Exercise
14.4. Enable versioning on the new bucket (see Exercise 14.6).
3.	Choose **Management**, choose **Replication**, and then choose **Add rule**.
4.	In the **Replication rule** wizard, under **Set Source**, choose **Entire Bucket**.
5.	Choose **Next**.
6.	On the **Set destination** page, under **Destination bucket**, choose your newly-created bucket.
7.	Choose the storage class for the target bucket. Under **Options**, select **Change the storage class for the replicated objects**. Select a storage class.
8.	Choose **Next**.
9.	For IAM, on the **Configure options** page, under **Select** role, choose **Create new role**.
10.	Choose **Next**.
11.	Choose **Save**.
12.	Load a new object in the source bucket. The object appears in the target bucket.

You have enabled cross-region replication, which can be used for compliance and disas-  ter recovery.
