#Exercise 13.1
##Create an Amazon S3 bucket for the Swagger Template
In this exercise, you use an AWS SAM template and a Swagger template to deploy your infrastructure. You will need to create an Amazon S3 bucket for the Swagger file.

**1.**	Create an Amazon S3 bucket.

    *aws s3 mb s3://my-bucket-name --region us-east-1*
     If the command was successful, you should see output similar to the following, which means the bucket has been created:
```
     make_bucket: my-bucket-name
```

**2.**	Upload the Swagger template.

    *aws s3 cp petstore-api-swagger.yaml s3://my-bucket-name/petstore-api-swagger.yaml*
    If the file was successfully uploaded, you should be able to navigate to the Amazon S3 bucket and see it. This file is for the Swagger template, and it is used to create the REST API inside the Amazon API Gateway. You have not yet deployed the API.

**3.**	Use AWS SAM to deploy your serverless infrastructure. To package your SAM tem- plate, run the following command:
```
    aws cloudformation package \
      --template-file ./petStoreSAM.yaml \
      --s3-bucket my-bucket-name \
      --output-template-file petStoreSAM-output.yaml \
      --region us-east-1
```
If the command was successful, you should see that the file has been uploaded, and a   new file called petStoreSAM-output.yaml has been created locally. You have pack- aged the AWS SAM template and converted it to a full AWS  CloudFormation template.  You will use this template in the next step to deploy the package to the Amazon API Gateway.

**4.**	Deploy the package.
```
    aws cloudformation deploy \
    --template-file ./petStoreSAM-output.yaml \
    --stack-name petStoreStack \
    --capabilities CAPABILITY_IAM \
    --parameter-overrides S3BucketName=s3://my-bucket-name/ petstore-api-swagger.yaml \
    --region us-east-1
```
If the command was successful, you should see that the *cloudformation* stack has been deployed. While it is in the process of deploying the resources, you will see something similar to the following:

*Waiting for stack create/update to complete*

This make take a few minutes. When it is finished deploying, the console displays the following message:

*Successfully created/updated stack – petStoreStack*

You have now successfully deployed the cloudformation stack and can view the resources it created inside the AWS Management Console under the **AWS CloudFormation service**.

**5.**	After the stack is created, run the command and write the results down for subse- quent steps:

*aws cloudformation describe-stacks --stack-name petStoreStack --region us-east-1 --query 'Stacks[0].Outputs[0].{PetStoreAPI:OutputValue}'*

  After running this command, the URL for the API is returned. Navigate to this URL to view the default page returned by the PetStore API. You will be changing this in the next exercise.



You have successfully completed the first exercise, created your AWS SAM template, and deployed it using AWS CloudFormation. Now your Amazon API Gateway is active, and you have the URL for accessing it.
