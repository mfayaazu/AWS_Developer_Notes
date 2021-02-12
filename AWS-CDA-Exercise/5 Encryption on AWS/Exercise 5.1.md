#Exercise 5.1
##Configure an Amazon S3 Bucket to Deny Unencrypted Uploads
In this exercise, you will enforce object encryption for an Amazon S3 bucket by using a
bucket policy to reject PUT requests without encryption headers.

1. Sign in to the AWS Management Console, and open the Amazon S3 console at *https://console.aws.amazon.com/s3/*.

2. Create a new bucket with a name of your choice.
3. Apply the following policy to the bucket:

  {
     "Version": "2012-10-17",
     "Statement": [

        {
         "Sid": "DenyIncorrectEncryption",
         "Effect": "Deny",
         "Principal": "*",
         "Action": "s3:PutObject",
         "Resource": "arn:aws:s3:::<bucket_name>/*",
         "Condition": {
           "StringNotEquals": {
              "s3:x-amz-server-side-encryption": "AES256"
            }
            },
         {
         "Sid": "DenyMissingEncryption",
         "Effect": "Deny",
         "Principal": "*",
         "Action": "s3:PutObject",
         "Resource": "arn:aws:s3:::<bucket_name>/*",
         "Condition": {
         "Null": {
         "s3:x-amz-server-side-encryption": true
       }
      }
     ]
    }

4. From the AWS Identity and Access Management (IAM) console, open the policy simulator.

5. Select an existing policy with access to the bucket that you created.

6. Test the PutObject Amazon S3 action with and without the x-amz-server-sideencryption header.

When you are uploading a new object or making a copy of an existing object, you can specify whether you want Amazon S3 to encrypt your data by adding the header to the API request.
