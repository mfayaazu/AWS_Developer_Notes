#Exercise 13.4
##Define an AWS lambda function locally
Now that you have a valid SAM template, you can define your AWS Lambda function locally. In this example, use Nodejs 8.10, but you can use any AWS Lambda supported language.
1.	Open your favorite IDE, and type the following Nodejs code:
```
      'use strict';

      //A simple Lambda function
      exports.handler = (event, context, callback) => {

          console.log('This is our local lambda function'); console.log('Creating a PetStore service');
          callback(null, "Hello " + event.Records[0].dynamodb.NewImage.Message.S + "! What kind of pet are you interested in?");
      }
```

2.	Save the file as *index.js*.
You have two files: an *index.js* and the SAM template. In the next exercise, you will gen- erate an event source that will be used as the trigger for the AWS Lambda function.
