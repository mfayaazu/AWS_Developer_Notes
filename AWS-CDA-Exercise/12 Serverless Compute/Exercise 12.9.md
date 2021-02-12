#Exercise 12.9
##Test the AWS lambda function
To  test the AWS Lambda function, use the AWS CLI to upload the CSV file to the Amazon  S3 bucket; then check whether the function transforms the data and puts the result file in the output bucket.

*aws s3 cp input-payroll-data.csv s3://shoe-company-2018-ingestion-csv-demo*

If everything executes successfully, in the output bucket that you created, you should see the transformed JSON file. You accepted input into one Amazon S3 bucket as a *.csv-*, transformed it to serverless by using AWS Lambda, and then stored the resulting *.json* file in a separate Amazon S3 bucket. If you do not see the file, retrace your steps through the exercises. It is a good idea to view the Amazon CloudWatch Logs, which can be found on the **Monitoring** tab in the AWS Lambda console. This way, you can determine whether there are any errors.
