#Exercise 10.2
##Setting up an AWS managed microsoft Ad
In this exercise, you will set up an AWS Managed Microsoft AD. Because this is an Active Directory managed by AWS, you do not have to consider the size or type of compute instances that will be running on this Active Directory. You will, however, have to choose the Amazon VPC that this service will run on.
This service is designed for high availability, so two domain controllers are created. Therefore, two corresponding subnets are used.
To simplify the installation, you will first create the necessary VPC, and then you will cre- ate the AWS Managed Microsoft AD.

**Step 1: Create a Virtual Private Cloud**
Create your Amazon VPC by using the AWS Management Console.
1.	In the AWS Services console navigation pane, choose **VPC** and then choose
**Your VPCs**.
2.	Note the VPCs used (to avoid address conflict), and choose **Create VPC**.
3.	In **VPC name**, enter, My Directory Service and specify an IPv4 CIDR block. Choose a CIDR block that is not currently used (for example, 10.30.0.0/16).
4.	For **Hardware tenancy**, select **Default**, and choose **Create**.
5.	After the VPC is created, return to the VPC dashboard and select **Subnets**.
6.	Choose **Create subnet**.
7.	In the **Create Subnet** dialog box, enter a name tag, choose the VPC you just created, select an Availability Zone, and specify an IPv4 CIDR block within that VPC (for example, 10.30.1.0/24).
8.	Choose **Create**.
9.	Repeat steps 6–8 to create a second subnet, making sure to choose a different Availability Zone and a different subnet other than the ones specified in step 7.

**Step 2: Create Your AWS Managed Microsoft AD Directory in AWS**
Create your AWS Managed Microsoft AD directory by using the AWS Management Console.
1.	In the AWS Directory Service console navigation pane, choose Directories and then choose **Set up directory**.
2.	On the **Select directory type** page, choose **AWS Managed Microsoft AD** and choose **Next**.
3.	On the **Enter directory information** page, provide the following information and then choose **Next**.
4.	For **Edition**, you can select either **Standard Edition** or **Enterprise Edition**. For this exercise, select **Standard Edition**.
For more information about editions, see AWS Directory Service for Microsoft Active Directory at *https://docs.aws.amazon.com/directoryservice/latest/admin-guide/what_is.html#microsoftad*.
5.	For **Directory DNS name**, enter **corp.example.com**.
6.	For **Directory NetBIOS name**, enter **corp**.
7.	For **Directory description**, enter **AWS DS Managed**.
8.	For **Admin password**, enter the password that you want to use for this account.  This admin account is automatically created during the directory creation process.
The password cannot include the word admin. The directory administrator password  is case-sensitive, and it must be 8–64 characters in length. It must also contain at  least one character from three of the following four categories:
■	Lowercase letters (a–z)
■	Uppercase letters (A–Z)
■	Numbers (0–9)
■	Nonalphanumeric characters (~!@#$%^&*_-+=`|\(){}[]:;"'<>,.?/)
9.	In **Confirm Password**, enter the password again.
10.	On the **Choose VPC and subnets** page, provide the following information and then choose **Next**.
a.	For **VPC**, choose the option that begins with *AWS-DS-VPC* and ends with *(10.0.0.0/16)*.
b.	For **Subnets**, choose the *10.0.128.0/20* and *10.0.144.0/20* public subnets.
c.	On the **Review & create** page, review the directory information and make any necessary changes. When the information is correct, choose **Create directory**.
Creating the directory takes 20–40 minutes. After the directory is created, the Status value changes to Active.

**Step 3: Management and Maintenance of AWS Managed Microsoft AD**
After AWS Managed Microsoft AD is set up, you are able to perform the following maintenance and management operations:
■	Manage the AWS applications and services available to users.
■	Share directories, see the Availability Zone and subnet of existing controllers, and add additional controllers.
■	Create trust relationships, establish IP routing, enable log forwarding, and use multi-factor authentication.
■	Create Amazon SNS email or text messages to inform you of changes in status to your directory, perform a point-in time backup (snapshot) of your directory, and modify the schema of your AWS Managed AD
directory.
