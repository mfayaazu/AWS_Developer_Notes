#Exercise 6.2
##Deploy a Blue/Green Solution
In this exercise, you will deploy a blue/green solution.
1. Sign in to your AWS account.
2. Navigate to your existing AWS Elastic Beanstalk environment and application or
upload the sample.
You can launch a sample application from this location:
*https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/tutorials.html*
3. Clone your environment or launch a new environment with your new version.
4. Deploy the second application version to the new environment. Test that the new
version is running.
5. From the new environment dashboard, select **Actions ➢ Swap Environment URLs**.
6. Under **Select an Environment to Swap**, select the current environment name.
7. Choose **Swap**.
The Elastic Beanstalk service swaps the CNAME records between the two
environments.
8. On the dashboard, under **Recent Events**, verify the swap.
You have successfully deployed a blue/green solution on AWS Elastic Beanstalk.
