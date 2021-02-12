#Exercise 4.8
##Add Users to the Amazon DynamoDB Table

With DynamoDB, there are fewer components to set up than there are for Amazon RDS. In this exercise, you’ll add users to your table. Experiment with updating and changing some of the code to add multiple items to the database.

To add users to the DynamoDB table, run the following script:
```
## Exercise 4.8
import boto3
import json
import datetime
## In this example we are not using uuid; however, you could use this to
autogenerate your user IDs.
## i.e. str(uuid.uuid4())
import uuid

## Create a DynamoDB Resource
dynamodb_resource = boto3.resource('dynamodb')
table = dynamodb_resource.Table('Users')

## Write a record to DynamoDB
response = table.put_item(

    Item={
        'user_id': '1234-5678',
        'user_email': 'someone@somewhere.com',
        'user_fname': 'Sam',
        'user_lname': 'Samuels'
    }
)

## Just printing the raw JSON response, you should see a 200 status code
print(json.dumps(response, indent=2, sort_keys=True))
```
After running the Python code, you receive a 200 HTTP Status Code from AWS. This
means that the user record has been added.

From the AWS Management Console, under DynamoDB, review the table to verify that
the user record was added.
