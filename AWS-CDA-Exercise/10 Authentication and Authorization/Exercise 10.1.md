#Exercise 10.1
##Setting up a Simple Active directory
In this exercise, you will set up an AWS Simple Active Directory (Simple AD). Simple AD is    a standalone directory that is powered by a Samba 4 Active Directory Compatible Server. Because it’s a standalone managed directory, you do not have to manage user accounts  and group memberships. This is achieved through the Microsoft Active Directory.

**Step 1: Create a Virtual Private Cloud**
In this step, you will use the Amazon Virtual Private Cloud (Amazon VPC) wizard in the Amazon VPC console to create a virtual private cloud. The wizard steps create a VPC with  a /16 IPv4 CIDR block and attach an internet gateway to the VPC.
1.	In the AWS Management Console navigation pane, choose **VPC** and then choose
**Launch VPC Wizard**.
2.	On the left, select **VPC with a Single Public Subnet**, and then choose **Select**.
To communicate with an Active Directory outside of AWS, you must create the Simple AD directory in a public subnet.
3.	On the next page, enter the following settings:
a.	Enter a valid, unused IP CIDER block (for example **10.40.0.0/16**).
b.	Choose a valid name (for example, **simple-ad-demo**).
c.	Choose a valid subnet (for example, **10.40.1.0/24**)
d.	Choose an Availability Zone in which to create the subnet. (Record your selection; you will need this information for the next step.)
4.	Choose **Create VPC**.
You  have launched a VPC that has a public subnet, an internet gateway attached to   it, and the necessary route table and security group configurations to allow traffic to flow between the subnet and the internet gateway. However, because Simple AD is a highly available service, you must create a second public subnet on this VPC.
5.	Navigate to the VPC dashboard and choose Subnets.
6.	Choose **Create Subnet**.
7.	On the next page, enter the following settings:
a.	Choose a name tag.
b.	Choose the VPC that you created in the previous steps.
c.	Choose an Availability Zone that is different from the one selected in the previ- ous steps.
d.	Choose a valid subnet.
8.	Choose **Create VPC**.
You have created a VPC that has two public subnets. When you create a Simple AD directory, each node is located in a different Availability Zone.

**Step 2: Create Your Simple AD Instance in AWS**
Create your AWS Managed Microsoft AD directory using the AWS Management Console.
1. 	In the AWS Directory Service console navigation pane, choose **Directories** and then choose **Set up directory**.
2.	On the **Select directory type** page, select **AWS Simple AD** and then choose **Next**.
3.	On the Enter **directory information** page, provide the following and then choose **Next**.
a.	Directory size (Small or Large).
b.	Directory DNS name.
c.	(Optional) Directory NetBIOS name (CORP, for example). If one is not provided, a name is created by default.
d.	An administrator password, which must be 8–24 characters in length. It must also contain at least one character from three of the following four categories: uppercase letters, lowercase letters, numbers, or nonalphanumeric characters.
e.	(Optional) Description of the directory. This is useful in tracking your services within AWS.
4.	On the **VPC and subnets** page, provide the following information, and then choose **Next**.
a.	For **VPC**, choose the VPC you created earlier (simple-ad-demo).
b.	Under **Subnets**, choose the two subnets you created for the domain controllers.
5.	Review your settings and choose **Create directory**.
It takes 5–10 minutes to create your directory. You may need to refresh the page. When the directory creation is complete, the Status value changes to Active.

Step 3: **Management and Maintenance of Simple AD Directory in AWS**
When the status changes to Active, the AWS Managed Microsoft AD directory is ready to do the following:
■	Manage the AWS applications and services available to users
■	Perform various maintenance activities, such as creating Amazon Simple Notification Service (Amazon SNS) email or text messages to inform you of changes in status to your directory, performing a point-in time backup (snapshot) of your directory, and modifying the schema of your AWS Managed AD directory
