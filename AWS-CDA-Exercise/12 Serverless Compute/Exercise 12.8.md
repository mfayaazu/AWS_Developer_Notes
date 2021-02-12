#Exercise 12.8
##Add the Amazon S3 event Trigger
In this exercise, add the trigger for Amazon S3 using AWS CLI for the s3api commands. The *notification-config.json* file was provided in the exercise files. Its contents are as follows:
```
{
          "LambdaFunctionConfigurations": [
              {
                  "Id": "s3PayrollFunctionObjectCreation",
                  "LambdaFunctionArn": "arn:aws:lambda:us-west-1:accountnumber:function: PayrollProcessing",
                  "Events": [
                     "s3:ObjectCreated:*"
              ],
              "Filter": {
                  "Key": {
                    "FilterRules": [
                        {
                          "Name": "suffix",
                          "Value": ".csv"
                        }
                  ]
              }
          }
      }
   ]
}
```

*aws s3api put-bucket-notification-configuration ––bucket shoe-company-2018-ingestion-csv-demo ––notification-configuration file://notification-config.json*

If the execution is successful, no response is sent. To verify that the trigger has been added to the AWS Lambda function, navigate to the AWS Lambda console inside the AWS Management Console, and verify that there is now an Amazon S3 trigger.
