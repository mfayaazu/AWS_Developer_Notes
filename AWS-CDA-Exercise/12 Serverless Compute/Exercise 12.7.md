#Exercise 12.7
##Give Amazon S3 permission to invoke an AWS lambda function
In this exercise, use the AWS Lambda CLI *add-permission* command to invoke the AWS Lambda function.

aws lambda add-permission --function-name PayrollProcessing --statement-id lambdas3permission --action lambda:InvokeFunction --principal s3.amazonaws.com
--source-arn arn:aws:s3:::shoe-company-2018-ingestion-csv-demo --source-account yourawsaccountnumber --region us-west-1

After you run this command and it is successful, you should receive a JSON response that looks similar to the following:
```
{
    "Statement": {
        "Sid": "lambdas3permission",
        "Effect": "Allow",
        "Principal": {
          "Service": "s3.amazonaws.com"
},
"Action": "lambda:InvokeFunction",
"Resource": "arn:aws:lambda:us-east-2:accountnumber:function:PayrollProce ssing",
"Condition": {
    "StringEquals": {
          "AWS:SourceAccount": "accountnumber"
        }
        "ArnLike": {
            "AWS:SourceArn": "arn:aws:s3:::shoe-company-2018-ingestion-csv-demo"
          }
      }
   }
}
```
This provides a function policy to the  AWS  Lambda  function  that  allows  the  S3  bucket that you created to call the action *lambda:InvokeFunction*. You can verify this by navigating to the AWS Lambda service inside the AWS Management  Console.  In  the Designer section, click the key icon to  view  permissions, and  under  **Function policy**,  you will see the policy you just created.
