#Exercise 13.7
##modify the AWS SAm template to include an Api locally
To make your pet store into an API, modify the *template.yaml*.
1.	Open the *template.yaml* file, and modify it to look like the following:
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
              Events:
                PetStore:
                  Type: Api
                  Properties:
                      Path: /
                      Method: any
```

2.	Save the *template.yaml* file.
You have modified the AWS SAM template to connect an Amazon API Gateway event for any method (GET, POST, and so on) to the AWS Lambda function. In the next exercise, you will modify the AWS Lambda function to work with the API.
