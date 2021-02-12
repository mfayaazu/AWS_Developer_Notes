#Exercise 12.4
##Prepare the AWS lambda function
To perform the conversion using the AWS CLI and the Python SDK, create the AWS Lambda function. The AWS CLI creates the AWS Lambda function. The Python SDK pro- cesses the files inside the AWS Lambda service.

In the following code, change the bucket names to bucket names you defined. The *lambda_handler* function passes the event parameter. This allows you to acquire the Amazon S3 bucket name.

Save this code to a file called *lambda_function.py*, and then compress the file.

>Note: You can use a descriptive file name; however, remember to update the handler code in Exercise 12.6.
```
import boto3
import csv
import json
import time
# The csv and json modules provide functionality for parsing
# and writing csv/json files. We can use these modules to
# quickly perform a data transformation
# You can read about the csv module here:
# https://docs.python.org/2/library/csv.html
# and JSON here:
# https://docs.python.org/2/library/json.html

# Create an s3 Resource: https://boto3.readthedocs.io/en/latest/guide/resources.html
s3 = boto3.resource('s3')
csv_local_file = '/tmp/input-payroll-data.csv'
json_local_file = '/tmp/output-payroll-data.json'

# Change this value to whatever you named the output s3 bucket in the previous exercise
output_s3_bucket = 'shoe-company-2018-final-json-demo'

def **lambda_handler**(event, context):
      # Need to get the bucket name
bucket_name = event['Records'][0]['s3']['bucket']['name']
key = event['Records'][0]['s3']['object']['key']

# Download the file to our AWS Lambda container environment try:
    s3.Bucket(bucket_name).download_file(key, csv_local_file)
except Exception as e:
    print(e)
    print('Error getting object {} from bucket {}. Make sure they exist and your bucket is in the same region as this function.'.format(key, bucket_name))
    raise e

# Open the csv and json files
csv_file = open(csv_local_file, 'r')
json_file = open(json_local_file, 'w')

# Get a csv DictReader object to convert file to json
dict_reader = csv.DictReader( csv_file )
# Create an Employees array for JSON, use json.dumps to pass in the string
json_conversion = json.dumps({'Employees': [row for row in dict_reader]})

# Write to our json file
json_file.write(json_conversion)
      # Close out the files
csv_file.close()
json_file.close()

# Upload finished file to s3 bucket
try:
    s3.Bucket(output_s3_bucket).upload_file(json_local_file, 'final-output- payroll.json')
except Exception as e:
    print(e)
    print('Error uploading object {} to bucket {}. Make sure the file paths are correct.'.format(key, bucket_name))
    raise e

print('Payroll processing completed at: ', time.asctime( time.localtime(time. time()) ) )
return 'Payroll conversion from CSV to JSON complete.'
```

After you create the code for the function, upload this file to Amazon S3 with the AWS CLI. This saves the code locally on your desktop and runs the following command. Be sure to compress the file.

*aws s3 cp lambda_function.zip s3://shoe-company-2018-ingestion-csv-demo*

If the following command successfully executed, you should see something similar to the following printed to the console:

*upload: .\lambda_function.zip to s3://shoe-company-2018-ingestion-csv-demo/lambda_ function.zip*

You may also verify that the file has been uploaded by using the AWS Management Console inside the Amazon S3 service.
