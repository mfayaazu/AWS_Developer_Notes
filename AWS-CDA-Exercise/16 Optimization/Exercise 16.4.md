#Exercise 16.4
##Create a launch Configuration and an AWS Auto Scaling group, and Schedule a Scaling Action
In this exercise, using AWS Management Console, you will create a launch configuration and AWS Auto Scaling policy, and verify the scheduled scaling action.
1.	To create a launch configuration, complete the following steps:
a.	Open the Amazon EC2 console at *https://console.aws.amazon.com/ec2/*.
b.	On the navigation pane, under **AWS Auto Scaling**, choose **Launch Configurations**.
On the next page, choose **Create launch configuration**.
c.	On the **Choose AMI** page, select your custom AMI.
d.	On the **Choose Instance Type** page, select a hardware configuration for your instance and choose **Next: Configure details**. Configure the remaining details.
e.	On the **Configure Details** page, do the following:
(i)	For **Name**, type a name for your launch configuration.
(ii)	For **Advanced Details, IP Address Type**, select **Assign a public IP address to every instance**.
f.	Choose **Skip to review**.
g.	On the **Review** page, choose **Edit security groups**. Follow the instructions to choose an existing security group, and then choose Review.
h.	On the **Review** page, choose **Create launch configuration**
i.	For **Select an existing key pair or create a new key pair** page, select one of the listed options.
j.	Select the acknowledgment check box, and then choose **Create launch configuration**.
2.	To create an AWS Auto Scaling group, complete the following steps:
a.	Select **Create an AWS Auto Scaling group using this launch configuration**.
b.	On the **Create AWS Auto Scaling Group** page, follow these steps:
(i)	For **Group name**, enter a name for your AWS Auto Scaling group.
(ii)	For **Group size**, enter **1** as the initial number of instances for your AWS Auto Scaling group.
(iii)	For **Network**, select the default VPC.
(iv)	For **Subnet**, select one or more subnets from the listed subnets.
c.	Choose **Next: Configure scaling policies**.
d.	On the **Configure scaling policies** page, select **Keep this group at its initial size** and then choose **Review**.
e.	On the **Review** page, choose **Create AWS Auto Scaling group**.
f.	On the **AWS Auto Scaling group creation status** page, choose **Close**.
3.	To schedule an AWS Auto Scaling action and verify that it’s working, complete the following steps:
a.	Select your AWS Auto Scaling group.
b.	On the **Schedule Actions** tab, select **Create Scheduled Action**.
c.	On **Schedule Action** page, follow these steps:
(i)	For **Name**, type name of the action.
(ii)	For **Max**, type **2**.
(iii)	For **Desired Capacity**, type **2**.
(iv)	For **Start Time**, select current day in Date (UTC), and type current UTC time + 2 minutes.
d.	Select **Save**.
e.	Select the **Instances** tab, refresh the tab in the next two minutes, and observe that a new Amazon EC2 instance was created.

In this exercise, you created a launch configuration and an AWS Auto Scaling group using  the launch group that you just created. To test whether automatic scaling is working, you added a Scaling action to launch a new Amazon EC2 instance by increasing capacity. You also verified that a new instance was added to the current capacity.
