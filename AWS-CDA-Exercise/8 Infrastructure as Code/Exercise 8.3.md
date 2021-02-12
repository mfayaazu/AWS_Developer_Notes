#Exercise 8.3
##monitor Stack update Activity
1.	Deploy the AWS CloudFormation code template, which provisions an Amazon S3 bucket in your account.
```
{
    "Resources" : {
       "ExampleBucket" : {
           "Type": "AWS::S3::Bucket"
         }
},
  "Outputs" : {
    "BucketName" : {
        "Value": { "Ref": "ExampleBucket" }
      }
    }
}
```
2.	After the stack is created, make note of the output value. This is the name of your Amazon S3 bucket.
3.	Use the template code to update the stack, and replace BUCKET_NAME with a name of your choice.
```
{
    "Resources" : {
       "ExampleBucket" : {
           "Type": "AWS::S3::Bucket",
           "Properties": {
              "BucketName": "BUCKET_NAME"
            }
        }
},
  "Outputs" : {
     "BucketName" : {
         "Value": { "Ref": "ExampleBucket" }
       }
     }
}
```
>Note: that a new bucket is created, and the original bucket is deleted. This is because you cannot change bucket names after initial creation, so a replacement must be provisioned.
