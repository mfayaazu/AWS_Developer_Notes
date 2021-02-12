#Exercise 4.12
##Remove the Amazon DynamoDB Table
In this exercise, you will remove the
 DynamoDB table that you created in Exercise 4.7.

To remove the table, run the following script:
```
## Exercise 4.12
import boto3
import json
import datetime
import uuid

## Create a DynamoDB Resource
dynamodb_client = boto3.client('dynamodb')

## Delete the Table
response = dynamodb_client.delete_table(TableName='Users')
print(json.dumps(response, indent=2, sort_keys=True))
```
The DynamoDB table is deleted, or it is in the process of being deleted. Verify the deletion from the AWS Management Console, under the DynamoDB service.
