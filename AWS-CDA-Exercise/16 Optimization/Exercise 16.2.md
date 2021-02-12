#Exercise 16.2
##Modify Amazon ebS Optimization for a running instance
In this exercise, you will use the Amazon EC2 console to enable the optimization for a running instance by modifying its Amazon EBS optimized instance attribute.
1.	Open the Amazon EC2 console at *https://console.aws.amazon.com/ec2/*.
2.	In the navigation pane, click **Instances**, and select the instance.
3.	Choose **Actions ➢ Instance State ➢ Stop**.
4.	In the **Confirmation** dialog box, choose **Yes ➢ Stop**.
    It can take a few minutes for the instance to stop.
5.	With the instance still selected, choose **Actions ➢ Instance Settings** and then choose **Change Instance Type**.
6.	In the **Change Instance Type** dialog box, do one of the following:
a.	If the instance type of your instance is Amazon **EBS–optimized**, EBS-optimized is selected by default, and you cannot change it. Choose **Cancel**.
b.	If the instance type of your instance supports Amazon EBS optimization, choose **EBS-optimized ➢ Apply**.
c.	If the instance type of your instance does not support Amazon EBS optimization, select an instance type from **Instance Type** that supports Amazon EBS optimiza- tion and then choose **EBS-optimized ➢ Apply**.
7.	Choose **Actions ➢ Instance State ➢ Start**.
You enabled the EBS optimization feature for a running Amazon EC2 instance using AWS Console.
