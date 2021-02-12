#Exercise 7.2
##Create an Application in AWS CodeDeploy
This exercise demonstrates how to use AWS CodeDeploy to perform an in-place
deployment to Amazon EC2 instances in your account.
1. Create a new application in the AWS CodeDeploy console.
For the compute platform type, select **EC2 On-premises**.
2. Create a new deployment group for your application. Specify the following values:
**Deployment type** In-place
**Environment configuration** Amazon EC2 instances
**Tag group** Create a tag group that is easy to identify, such as a “Name” for the key, and “CodeDeployInstance” as the value.
**Load balancer** Clear the **Enable load balancing** check box.
3. Launch new **Amazon EC2 instance**.
Make sure to specify the tag value chosen in the previous step.
4. Download the **sample application bundle** to your local machine for future updates.
Sample application bundles for each operating system can be found using the following links:
**Windows Server** *https://docs.aws.amazon.com/codedeploy/latest/userguide/tutorials-windows.html*
**Amazon Linux or Red Hat Enterprise Linux (RHEL)** *https://docs.aws.amazon.com/codedeploy/latest/userguide/tutorials-wordpress.html*
5. Create a deployment group, and verify that the sample application **deploys**.
6. **Update** the application code, and **submit** a new deployment to the deployment group.
7. Verify your changes after the deployment completes
