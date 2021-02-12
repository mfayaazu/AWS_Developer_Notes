#Exercise 13.3
##Define an AWS SAm Template
In this exercise, you will develop an AWS Lambda function locally  and  then  test  that Lambda function using  the  AWS  SAM  CLI.  To  perform  this  exercise  successfully,  you must have AWS SAM CLI installed. For information on how to install the  AWS  SAM  CLI, review the following documentation: *https://github.com/awslabs/aws-sam-cli*. The following steps assume that you have a working AWS SAM CLI installation.
1.	Once you have installed AWS SAM CLI, open your favorite integrated development environment (IDE) and define an AWS SAM template.
2. Enter the following in your template file:
```
      AWSTemplateFormatVersion: '2010-09-09'
      Transform: AWS::Serverless-2016-10-31

      Description: Welcome to the Pet Store Demo

      Resources:
        PetStore:
          Type: AWS::Serverless::Function
          Properties:
            Runtime: nodejs8.10
            Handler: index.handler
```
3.	Save the file as *template.yaml*.
You have created the SAM template and saved the file locally. In subsequent exercises, you will use this information to execute an AWS Lambda function.
