#Exercise 4.6
##Remove Amazon RDS Database and Security Group
You’ve created an Amazon RDS DB instance and added data to it. In this exercise, you will
remove a few resources from your account. Remove the Amazon RDS instance first.

To remove the Amazon RDS instance and the security group, run the following script:
```
## Exercise 4.6
import boto3
import json
import datetime

## Create the client for Amazon RDS
rds_client = boto3.client('rds')

## Delete the RDS Instance
response = rds_client.delete_db_instance(
    DBInstanceIdentifier=rds_identifier,
    SkipFinalSnapshot=True)

print('RDS Instance is being terminated...This may take several minutes.')

waiter = rds_client.get_waiter('db_instance_deleted')
waiter.wait(DBInstanceIdentifier=rds_identifier)

## We must wait to remove the security groups until the RDS database has been
 deleted, this is a dependency.
print('The Amazon RDS database has been deleted. Removing Security Groups')

## Create the client for Amazon EC2 SG
ec2_client = boto3.client('ec2')

## Get the Security Group ID Number
response = ec2_client.describe_security_groups(
    GroupNames=[
        sg_name
    ])
sg_id_number = json.dumps(response['SecurityGroups'][0]['GroupId'])
sg_id_number = sg_id_number.replace('"','')

## Delete the Security Group!
response = ec2_client.delete_security_group(
    GroupId=sg_id_number
    )

print('Cleanup is complete!')
```
After running the Python code, the following message is displayed:
```
 Cleanup is complete!
 ```
The Amazon RDS database and the security group are removed. You can verify this from
the AWS Management Console.
