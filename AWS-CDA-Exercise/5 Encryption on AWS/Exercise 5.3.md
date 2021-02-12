#Exercise 5.3
##Create an AWS KMS Customer Master Key with the Python SDK
In this exercise, you will create a new AWS KMS customer master key (CMK) using the
AWS Command Line Interface (AWS CLI). You will use Python as one of the supported
programming languages.

1. To create the AWS KMS CMK, run the following Python script:
```
   import boto3
   import json
   kms_client = boto3.client('kms',
   region_name='us-west-1')
   response = kms_client.create_key(

       Description='My KMS Key',
       KeyUsage='ENCRYPT_DECRYPT',
       Origin='AWS_KMS',
       Tags=[
       {
               'TagKey': 'KeyPurpose',
               'TagValue': 'dev-on-aws-key'
       },
       ]
       )
       print(response)
```
2. To list the CMKs and describe the available keys, run the following script:
```
import boto3
import json

# List the KMS Keys by ID

kms_client = boto3.client('kms', region_name='us-west-1')
try:

    response = kms_client.list_keys()
    except ClientError as e:
    logging.error(e)
    print(json.dumps(response, indent=4, sort_keys=True))
```
3. To describe the keys inside AWS KMS, run the following script:
```
import boto3
import json

## List the KMS Keys by ID
kms_client = boto3.client('kms', region_name='us-west-1')

## Describe the Keys
for key in response['Keys']:

    try:
        key_info = kms_client.describe_key(KeyId=key['KeyArn'])
        key_id = key_info['KeyMetadata']['KeyId']
        key_arn = key_info['KeyMetadata']['Arn']
        key_state = key_info['KeyMetadata']['KeyState']
        key_description = key_info['KeyMetadata']['Description']
        print('Key ID: ' + key_id)
        print('Key ARN: ' + key_arn)
        print('Key State: ' + key_state)
        print('Key Description: ' + key_description)
        print('-------------------------------------')
       except ClientError as e:
       logging.error(e)
```
4. To delete the AWS KMS key, run the following script:
```
import boto3

kms_client = boto3.client('kms', region_name='us-west-1')
response = kms_client.schedule_key_deletion(

    KeyId='fasdf1-2451b-151-bea2-easdfg8',
    PendingWindowInDays=7
    )
    print(response, indent=4, sort_keys=True)
```
