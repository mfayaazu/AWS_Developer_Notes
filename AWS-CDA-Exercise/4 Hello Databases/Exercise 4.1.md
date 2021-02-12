#Exercise 4.1
##Create a Security Group for the Database Tier on Amazon RDS

Before you can create your first Amazon RDS database, you must create a security group so that you can allow traffic from your development server to communicate with the database tier. To do this, you must use an Amazon EC2 client to create the security group. Security groups are a component of the Amazon EC2 service, even though you can use them as part of Amazon RDS to secure your database tier.
To create the security group, run the following script:

```
import boto3
import json
import datetime

# Let's create some variables we'll use throughout these Excercises in Chapter 4
# NOTE: Here we are using a CIDR range for incoming traffic. We have set it to 0.0.0.0/0 which means
# ANYONE on the internet can access your database if they have the username and the password
# If possible, specify you're own CIDR range. You can figure out your CIDR range by visiting the following link
# *https://www.google.com/search?q=what+is+my+ip*
# In the variable don't forget to add /32!
# If you aren't sure, leave it open to the world

# Variables
sg_name = 'rds-sg-dev-demo'
sg_description = 'RDS Security Group for AWS Dev Study Guide'
my_ip_cidr = '0.0.0.0/0'


# Create the EC2 Client to create the Security Group for your Database
ec2_client = boto3.client('ec2')

# First we need to create a security group
response = ec2_client.create_security_group(
      Description=sg_description,
      GroupName=sg_name)
print(json.dumps(response, indent=2, sort_keys=True))
# Now add a rule for the security group
response = ec2_client.authorize_security_group_ingress(
    CidrIp=my_ip_cidr,
    FromPort=3306,
    GroupName=sg_name,
    ToPort=3306,
    IpProtocol='tcp'
    )
print("Security Group should be created! Verify this in the AWS Console.")
```


After running the Python code, verify that the security group was created successfully from the AWS Management Console. You can find this confirmation under the VPC or Amazon EC2 service
