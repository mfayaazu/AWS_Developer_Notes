#Exercise 4.7
##Create an Amazon DynamoDB Table

Amazon DynamoDB is a managed NoSQL database. One major difference between
DynamoDB and Amazon RDS is that DynamoDB doesn’t require a server that is running
in your VPC, and you don’t need to specify an instance type. Instead, create a table.

To create the table, run the following script:
```
## Exercise 4.7
import boto3
import json
import datetime

dynamodb_resource = boto3.resource('dynamodb')

table = dynamodb_resource.create_table(
    TableName='Users',
    KeySchema=[

        {
            'AttributeName': 'user_id',
            'KeyType': 'HASH'
        },
        {
            'AttributeName': 'user_email',
            'KeyType': 'RANGE'
        }
 ],

 AttributeDefinitions=[

     {
         'AttributeName': 'user_id',
         'AttributeType': 'S'
     },
     {
         'AttributeName': 'user_email',
         'AttributeType': 'S'
     }
  ],

 ProvisionedThroughput={
     'ReadCapacityUnits': 5,
     'WriteCapacityUnits': 5

   }

)

print("The DynamoDB Table is being created, this may take a few minutes...")

table.meta.client.get_waiter('table_exists').wait(TableName='Users')

print("Table is ready!")
```
After running the Python code, the following message is displayed:
```
Table is ready!
```
From the AWS Management Console, under DynamoDB, verify that the table was created.
