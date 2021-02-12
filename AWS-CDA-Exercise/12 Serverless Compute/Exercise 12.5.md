#Exercise 12.5
##Create AWS iAm roles
In this exercise, create an AWS IAM role so that the AWS Lambda function has the correct permissions to execute the function with the AWS CLI. Create a JSON file of the trust rela- tionship, which allows the AWS Lambda service to assume this particular IAM role with the Security Token Service.

Also create a policy document. A predefined policy document was distributed in the code example that you downloaded in Exercise 12.1. However, if you prefer to create the file manually, you can do so. The following is required for the exercise to work correctly:
```
lambda-trust-policy.json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "Service": "lambda.amazonaws.com"
            },
            "Action": "sts:AssumeRole"
          }
      ]
}
```
After the *lambda-trust-policy.json* document has been created, run the following command to create the IAM role:

aws iam create-role -–role-name PayrollProcessingLambdaRole --description "Provides AWS Lambda with access to s3 and cloudwatch to execute the PayrollProcessing function" --assume-role-policy-document file://lambda-trust- policy.json

A JSON object returns. Copy the RoleName and ARN roles for the next steps.
```
{
    "Role": {
        "AssumeRolePolicyDocument": {
           "Version": "2012-10-17",
           "Statement": [
                {
                    "Action": "sts:AssumeRole",
                    "Effect": "Allow",
                    "Principal": {
                        "Service": "lambda.amazonaws.com"
                }
            }
         ]
      },
    "RoleId": "roleidnumber",
    "CreateDate": "2018-05-19T17:30:05.020Z",
    "RoleName": "PayrollProcessingLambdaRole",
    "Path": "/",
    "Arn": "arn:aws:iam::accountnumber:role/PayrollProcessingLambdaRole"
   }
}
```
  After you create an AWS role, attach a policy to the role. There are two types of AWS policies: AWS managed and customer managed.  AWS  creates  predefined  policies that you can use called AWS managed policies. You may create customer managed policies specific to your requirements.

  For this example, you will use an AWS managed policy built for AWS Lambda called AWSLambdaExecute. This provides AWS Lambda access to Amazon CloudWatch Logs and Amazon S3 GetObject and PutObject API calls.

aws iam attach-role-policy --role-name PayrollProcessingLambdaRole --policy-arn arn:aws:iam::aws:policy/AWSLambdaExecute

If this command successfully executes, it does not return results. To  verify that  the  IAM role has been properly  configured,  from  the  AWS  Management  Console,  go  to  the IAM service. Click Roles, and search for *PayrollProcessingLambdaRole*. On the **Permissions tab**, verify that the *AWSLambdaExecute* policy has been attached. On the Trust relationships tab, verify that the trusted entities states the following: “The identify provider(s) lambda.amazonaws.com.”

You have successfully uploaded the Python code that has been compressed to Amazon S3, and you created an IAM role. In the next exercise, you will create the AWS Lambda function.
