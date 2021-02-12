#Exercise 4.10
##Write Data to the Table as a Batch Process
In this exercise, you will write data to the table through a batch process.

To write data using a batch process, run the following script:
```
## Exercise 4.10
import boto3
import json
import datetime
import uuid

## Create a DynamoDB Resource
dynamodb_resource = boto3.resource('dynamodb')
table = dynamodb_resource.Table('Users')

## Generate some random data
with table.batch_writer() as user_data:
   for i in range(100):

       user_data.put_item(
           Item={
               'user_id': str(uuid.uuid4()),
               'user_email': 'someone' + str(i) + '@somewhere.com',
               'user_fname': 'User' + str(i),
               'user_lname': 'UserLast' + str(i)
           }
           )
 print('Writing record # ' + str(i+1) + ' to DynamoDB Users Table')
 print('Done!')
```
After running the Python code, the last few lines read as follows:
```
Writing record # 300 to DyanmoDB Users Table Done!
```
From the AWS Management Console, under DynamoDB Table, verify that the users were
written to the table.
