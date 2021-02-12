#Exercise 13.5
##Generate an event Source
Now that you have a valid SAM template and a valid AWS Lambda Nodejs 8.10 function, you can generate an event source.
1.	Inside your terminal, type the following to generate an event source:
```
sam local generate-event dynamodb update > event.json
```
  This will generate an Amazon DynamoDB update event. For a list of all of the event sources, type the following:
```
sam local generate-event –help
```
2.	Modify the event source JSON file (event.json). On line 17, change New Item! to your first and last names.
```
"S": "John Smith"
```
You have now configured the three pieces that you need: the AWS SAM template, the  AWS Lambda function, and the event source. In the next exercise, you will be able to run the AWS Lambda function locally.
