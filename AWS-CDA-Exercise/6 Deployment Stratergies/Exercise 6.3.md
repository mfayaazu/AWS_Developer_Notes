#Exercise 6.3
##Change Your Environment Configuration on AWS Elastic Beanstalk
In this exercise, you will change your environment configuration on AWS Elastic
Beanstalk. Use an existing application that is running on Elastic Beanstalk.
1. Sign in to your AWS account.
2. Navigate to your existing AWS Elastic Beanstalk environment and application.
3. Choose Configuration.
4. On the **Capacity Configuration** tab, choose **Modify**.
5. Under **Auto Scaling Group**, select **Load balanced**.
6. In the Instances row, change Max to 4 and Min to 2
7. On the **Modify capacity** page, choose **Save**.
8. On the **Configuration overview** page, choose **Apply**.
9. On the warning message, choose **Confirm**.
The environment might take a few minutes to update. After your environment is
updated, verify your changes.
10. Navigate to the Amazon EC2 service dashboard.
11. Choose **Load Balancers**.
12. Check for the instance-id value that matches your Elastic Beanstalk environment
instance-id value and view the load balancers.
You have successfully changed an environment configuration on AWS Elastic Beanstalk
