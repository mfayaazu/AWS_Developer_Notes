#Exercise 12.2
##Create an Amazon S3 bucket for final output JSon
To create the second bucket for final output, run the following:
```
  import boto3
# Variables for the bucket name and the region we will be using.
# Important Note: s3 Buckets are globally unique, as such you need to change the name of the bucket to something else.
# Important Note: If you would like to use us-east-1 as the region, when making the s3.create_bucket call, then do not specify any region.
bucketName = "shoe-company-2018-final-json-demo"
bucketRegion = "us-west-1"
# Creates an s3 Resource; this is a higher level API type service for s3.
s3 = boto3.resource('s3')
# Creates a bucket
bucket = s3.create_bucket(ACL='private',Bucket=bucketName,CreateBucketConfiguratio n={'LocationConstraint': bucketRegion})
```

In the first exercise, you created the initial bucket for ingestion of the .csv file. This bucket will be used for the final JSON output. Again, if you see any errors here, look at the error logs. Verify that the bucket exists inside the Amazon S3 console. You  will verify the   buckets programmatically in the next exercise.
