#Exercise 6.4
##Update an Application Version on AWS Elastic Beanstalk
In this exercise, you will update an application version on AWS Elastic Beanstalk from the
AWS Management Console.
1. Sign in to your AWS account.
2. Upload a second version your application that matches the configuration for your
current running environment.
If you are using a sample solution application, you can find other versions at the following address:
*https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/GettingStarted.html#GettingStarted.Walkthrough.DeployApp*
3. On the **AWS EB applications** page, select *getting-started-app*.
4. Select *GettingStartedApp-env*.
5. In **Overview**, choose **Upload and Deploy**.
6. Select **Choose File** and upload the next version of your source bundle that you created or downloaded.

The console is automatically populated with the version label based on the name
of the archive that you upload. For later deployments, if you use a source bundle with
the same name, you must type a unique version label.
  7. Choose **Deploy**. Elastic Beanstalk deploys your application to your Amazon EC2 instances.
You can view the status of the deployment on the environment’s dashboard. The
Environment Health status turns gray while the application version is being updated. When deployment is complete, Elastic Beanstalk executes an application health check. The status reverts to green when the application responds to the health check. The environment dashboard shows the new running version as the new version label. Your new application version is added to the table of application versions.
  8. To view the table, select **Application Versions**.
You have updated an application version on AWS Elastic Beanstalk.
