#Exercise 13.9
##run Amazon Api gateway locally
Now that you have everything defined, run Amazon API Gateway locally.
1.	Open a terminal and type the following:
```
sam local start-api
```
You will see output that looks like the following. Take note of the URL.
```
2018-10-11 23:05:25 Mounting PetStore at http://127.0.0.1:3000/hello [GET]
2018-10-11 23:05:25 You can now browse to the above endpoints to invoke your functions. You do not need to restart/reload SAM CLI while working on your functions changes will be reflected instantly/automatically. You only need to restart SAM CLI if you update your AWS SAM template
2018-10-11 23:05:25 * Running on http://127.0.0.1:3000/ (Press CTRL+C to quit)
```
2.	Open a web browser, and navigate to the previous URL. You will see the following message:
*Message: "Hello! Welcome to the Pet Store. What kind of Pet are you interested in?"*

When you navigate to the URL, the local API Gateway  forwards  the  request  to  AWS Lambda, which is also running locally, provided by *index.js*. You  can now build server-  less applications locally. When you are ready to deploy to a development or production environment, deploy the serverless applications to the AWS Cloud with AWS  SAM.  This allows developers to iterate through their code quickly and make improvements locally.
