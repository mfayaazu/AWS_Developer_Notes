#Exercise 13.8
##Modify your AWS lambda function for the Api
After you have defined an API, modify your AWS Lambda function.
1.	Open the *index.js* file, and make the following changes:
```
    'use strict';

    //A simple Lambda function
    exports.handler = (event, context, callback) => {

        console.log('DEBUG: This is our local lambda function');
        console.log('DEBUG: Creating a PetStore service');

        callback(null, {
            statusCode: 200,
            headers: { "x-petstore-custom-header": "custom header from petstore service" },
            body: '{"message": "Hello! Welcome to the PetStore. What kind of Pet are you interested in?"}'
        })

}
```
2.	Save the *index.js* file.
You have modified the AWS Lambda function to respond to an API REST request. How- ever, you have not actually executed anything—you will do that in the next exercise.
