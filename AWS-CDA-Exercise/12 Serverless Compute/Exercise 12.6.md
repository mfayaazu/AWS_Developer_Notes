#Exercise 12.6
##Create the AWS lambda function
In this exercise, create the AWS Lambda function. You can view the AWS Lambda API ref- erence here:

*https://docs.aws.amazon.com/cli/latest/reference/lambda/index.html*
>Note: For the --handler parameter, make sure that you specify the name of the .py file you created in Exercise 12.4. Also, make sure that for the S3Key parameter, you specify the name of the compressed file inside the Amazon S3 bucket.

Run this AWS CLI command:

aws lambda create-function --function-name PayrollProcessing --runtime python3.7

--role arn:aws:iam::accountnumber:role/PayrollProcessingLambdaRole --handler lambda_function.lambda_handler --description "Converts Payroll CSVs to JSON and puts the results in an s3 bucket." --timeout 3 --memory-size 128 --code S3Bucket=shoe-company-2018-ingestion-csv-demo,S3Key=lambda_function.zip --tags Environment="Production",Application="Payroll" --region us-west-1

If the command was successful, you receive a JSON response similar to the following:
```
{
    "FunctionName": "PayrollProcessing",
    "FunctionArn": "arn:aws:lambda:us-east-2:accountnumber:function: PayrollProcessing",
    "Runtime": "python3.7",
    "Role": "arn:aws:iam::accountnumber:role/PayrollProcessingLambdaRole", "Handler": "payroll.lambda_handler",
    "CodeSize": 1123,
    "Description": "Converts Payroll CSVs to JSON and puts the results in an s3 bucket.",
    "Timeout": 3,
    "MemorySize": 128,
    "LastModified": "2018-12-10T06:36:27.990+0000",
    "CodeSha256": "NUKm2kp/fLzVr58t8XCTw6YGBmxR2E1Q9MHuW11QXfw=",
    "Version": "$LATEST",
    "TracingConfig": { "Mode": "PassThrough"
    },
    "RevisionId": "ae30524f-26a9-426a-b43a-efa522cb1545"
    }
  ```


You have successfully created the AWS Lambda function. You can verify this from the AWS Management Console and opening the AWS Lambda console
