#Exercise 4.3

##Obtain the Endpoint Value for the Amazon RDS Instance

Before you can start using the Amazon RDS instance, you must first specify your endpoint. In this exercise, you will use the Python SDK to obtain the value.

To obtain the Amazon RDS endpoint, run the following script:
```
# Exercise 4.3
import boto3
import json
import datetime


# Just a quick helper function for date time conversions, in case you want to
 print the raw JSON
 def date_time_converter(o):
     if isinstance(o, datetime.datetime):
        return o.__str__()

 # Variables
 rds_identifier = 'my-rds-db'

 # Create the client for Amazon RDS
 rds_client = boto3.client('rds')

 print("Fetching the RDS endpoint...")
 response = rds_client.describe_db_instances(
     DBInstanceIdentifier=rds_identifier
 )

 rds_endpoint = json.dumps(response['DBInstances'][0]['Endpoint']['Address'])
 rds_endpoint = rds_endpoint.replace('"','')
 print('RDS Endpoint: ' + rds_endpoint)
```
 After running the Python code, the following status is displayed:
```
Fetching the RDS endpoint.. RDS Endpoint:<endpoint_name>
```
 If the endpoint is not returned, from the AWS Management Console, under the RDS service,
 verify that your Amazon RDS database instance was created.
