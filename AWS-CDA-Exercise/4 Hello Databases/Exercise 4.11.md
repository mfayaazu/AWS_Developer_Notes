#Exercise 4.11
##Scan the Amazon DynamoDB Table
In this exercise, you will scan the entire table.

To scan the table, run the following script:
```
## Exercise 4.11
import boto3
import json
import datetime
import uuid

## Create a DynamoDB Resource

dynamodb_resource = boto3.resource('dynamodb')
table = dynamodb_resource.Table('Users')

## Let's do a scan!
response = table.scan()

print('The total Count is: ' + json.dumps(response['Count']))
print(json.dumps(response['Items'], indent=2, sort_keys=True))
```
As you learned in this chapter, scans return the entire dataset located in the table. After running the script, all of the users are returned.
