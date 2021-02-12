#Exercise 12.1
##Create an Amazon S3 bucket for CSv ingestion
To solve this, create two Amazon S3 buckets (CSV ingestion and JSON output) and an AWS Lambda function to process the file.
After you export the CSV file, upload the file to Amazon S3. First, create an Amazon S3 bucket with the following Python code:
```
  import boto3
# Variables for the bucket name and the region we will be using.
# Important Note: s3 Buckets are globally unique, as such you need to change the name of the bucket to something else.
# Important Note: If you would like to use us-east-1 as the region, when making the s3.create_bucket call, then do not specify any region.

bucketName = "shoe-company-2018-ingestion-csv-demo"
bucketRegion = "us-west-1"

# Creates an s3 Resource; this is a higher level API type service for s3. s3 = boto3.resource('s3')
# Creates a bucket
bucket = s3.create_bucket(ACL='private',Bucket=bucketName,CreateBucketConfiguration
={'LocationConstraint': bucketRegion})
```

This Python code creates a resource for interacting with the Amazon S3 service. After the resource is created, you can call the function .create_bucket to create a bucket.

After executing this Python code, verify that the bucket has been successfully created inside the Amazon S3 console. If it is not successfully created, the most likely cause is that the bucket name is not unique; therefore, renaming the bucket should solve the issue.
