#Exercise 13.2
##Edit the HTML Files
In steps 1 through 5, you are going to update the URL inside your .html files to point to      the Amazon API Gateway stage that you have created. You do this so that your web appli- cation (.html files) knows the endpoint where to send your pet data.
1.	Open index.html in the project folder and locate line 68 to find the variable named api_gw_endpoint. Input the value you retrieved from the previous command in Exercise 13.1.
```
var api_gw_endpoint = "https://cdvhqasdfnk444fe.execute-api.us-east-1
.amazonaws.com/PetStoreProd/"
```
2.	Open pets.html.
3.	Input the value you received from the last command on line 96, and add /pets to the end of the string:
```
var api_gw_endpoint = "https://cdvhqasdfnk444fe.execute-api.us-east-1. amazonaws.com/PetStoreProd/pets"
```
4.	Open add-pet.html.
5.	Input the value you received from the last command on line 87, and add /pets to the end.
```
var api_gw_endpoint = "https://cdvhqasdfnk444fe.execute-api.us-east-1.amazonaws.com/PetStoreProd/pets"
```
6.	Create a new Amazon S3 bucket for your website.
```
aws s3 mb s3://my-bucket-name --region us-east-1
```
 7. Copy the project files to the website.
```
aws s3 cp . s3://my-bucket-name --recursive aws s3 rm s3://my-bucket-name/sam –recursive
```
  Here you are uploading all the files from your project folder to Amazon S3 and then removing the SAM template from the bucket. You do not want others to have access to your template files and AWS Lambda functions. You want others to have access only to the end application.

  8.	Change the Amazon S3 bucket name inside of the policy.json to your bucket name. This will be on line 12.
  9.	Enable public read access for the bucket:
```
aws s3api put-bucket-policy --bucket my-bucket-name --policy file://policy.json
```
If successful, this command will not return any information. You are enabling the Amazon S3 bucket to be publicly accessible, meaning that everyone can access your website.

  10.	Enable the static website.
```
aws s3 website s3://my-bucket-name/ --index-document index.html --error- document index.html
```
The Amazon S3 bucket now acts as a web server and is running your pet store application.

  11.	Navigate to the website.

url: http://my-bucket-name.s3-website-us-east-1.amazonaws.com/index.html

  12.	Navigate Amazon API Gateway, AWS Lambda, Amazon DynamoDB, and the AWS SAM template to view the configuration.
Now that the application has been deployed, you can view all the individual components inside the AWS Management Console.
Inside Amazon API Gateway, you should see the *PetStoreAPIGW*. If you review the resources, you will see the various HTTP methods that you are allowing for your API.
In AWS Lambda, two functions were created: *savePet* for saving pets to Amazon Dy- namoDB and *getPets* for retrieving pets stored in Amazon DynamoDB.
In Amazon DynamoDB, you should have a table called *PetStore*. You can view the items in this table, though by default there should be none. After you create your first pet, however, you will be able to see some items in the table.
You can view the AWS SAM template and the AWS CloudFormation stack to see exactly how each of these resources were created.

>Warning: With YAML, tab indentations are extremely important. Make sure that you have a valid YAML template. There are a variety of tools that you can use to validate YAML syntax. You can use the following websites to validate the YAML:
      https://codebeautify.org/yaml-validator
      http://www.yamllint.com/
If you want to perform client-side validation and not use a website, a num- ber of IDEs support YAML validation. Refer to your IDE documentation to check for YAML support.
