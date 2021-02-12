#Exercise 7.3
##Create an AWS CodeBuild Project
This exercise demonstrates how to use AWS CodeBuild to perform builds and the compilation of artifacts prior to deployment to Amazon EC2 instances.
1. Create an Amazon S3 bucket to hold artifacts.
2. Upload two or more arbitrary files to the bucket.
3. Use the AWS CodeBuild console to create a build project with the following settings:
**Project name** Provide a name of your choice.
**Source** Use Amazon S3.
**Bucket** Provide the name of the bucket you created.
**S3 object key** Provide the name of one of the objects you uploaded.
**Environment image** Select the **Managed Image** type.
**Operating system** Use **Ubuntu**.
**Runtime** Use **Python**.
**Runtime version** Select a version of your choice.
**Service role** Select **New Service Role**.
**Role name** Provide a name for your service role.
**Build specifications** Select **Insert Build Commands**.
**Build commands** Select **Switch To Editor** and enter the following. Replace the Amazon S3 object paths with paths to the objects you uploaded to your bucket.
```
version: 0.2
phases:
 build:
 commands:
 - aws s3 cp s3://yourbucket/file1 /tmp/file1
 - aws s3 cp s3://yourbucket/file2 /tmp/file2
artifacts:
 files:
 - /tmp/file1
 - /tmp/file2
```
**Artifact Type** Use **Amazon S3**.
**Bucket name** Select your Amazon S3 bucket.
**Artifacts packaging** Select **Zip**.
4. Save your build project.
5. Run your build project, and observe the output archive file created in your Amazon S3 bucket.
