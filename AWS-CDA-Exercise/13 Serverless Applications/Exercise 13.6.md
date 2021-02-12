#Exercise 13.6
##run the AWS lambda function
Trigger and execute the AWS Lambda function.
1.	In your terminal, type the following to execute the AWS Lambda function:
```
sam local invoke "PetStore" -e event.json
```
You will see the following message:
*Hello Casey Gerena! What kind of pet are you interested in?*

The AWS  Lambda  Docker  image  is  downloaded  to  your  local  environment,  and the *event.json* serves as all of the data that will be received as an event source to the AWS Lambda function. Inside the AWS SAM template, you will have given this
function the name *PetStore*; however, you can define as many functions as you need to in order to build your application.
