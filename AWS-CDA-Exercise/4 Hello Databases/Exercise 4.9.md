#Exercise 4.9
##Look Up a User in the Amazon DynamoDB Table
In this exercise, you look up the one user you’ve added so far.

To look up users in the DynamoDB table, run the following script:
```
## Exercise 4.9
import boto3
from boto3.dynamodb.conditions import Key
import json
import datetime

## Create a DynamoDB Resource
dynamodb_resource = boto3.resource('dynamodb')
table = dynamodb_resource.Table('Users')

## Query a some data
response = table.query(

    KeyConditionExpression=Key('user_id').eq('1234-5678')
)

## Print the data out!
print(json.dumps(response['Items'], indent=2, sort_keys=True))
```
After running the Python code, the query results are returned in JSON format showing a single user.
