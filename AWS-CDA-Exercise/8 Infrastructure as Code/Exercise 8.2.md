#Exercise 8.2
##Troubleshoot a failed Stack deletion
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
2.	Upload several files and objects to the Amazon S3 bucket that the template creates.
3.	Delete the stack and monitor progress until it fails.

     Note the error output by AWS CloudFormation when the stack reaches the *DELETE_ FAILED* state.
4.	Delete all files from the Amazon S3 bucket.
5.	Attempt to delete the stack again, but do not enable the option to retain the bucket.
