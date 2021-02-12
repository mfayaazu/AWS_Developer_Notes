#Exercise 14.3
##Create and Attach an Amazon efS volume
In this exercise, you will create a new Amazon EFS volume and attach it to a running instance.
1.	While signed in to the AWS Management Console, open the Amazon EC2 console at *https://console.aws.amazon.com/ec2*.
If you don’t see a running Linux instance, launch a new instance.
2.	Open the Amazon EFS service dashboard. Choose **Create File System**.
3.	Select the Amazon VPC where your Linux instance is running.
4.	Accept the default mount targets, and make a note of the security group ID assigned to the targets.
5.	Choose any settings, and then create the file system.
6.	Assign the same default security group used by the file system to your Linux instance.
7.	Log in to the console of the Linux instance, and install the NFS client on the Amazon EC2 instance. For Amazon Linux, use the following command:
*sudo yum install –y nfs-utils*
8.	Create a new directory on your Amazon EC2 instances, such as *awsdev: sudo mkdir awsdev*.
9.	Mount the file system using the DNS name:
*sudo mount –t nfs4 –o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600, retrains=2 fs-12341234.efs.region-1.amazonaws.com:/ awsdev*

You have mounted the Amazon EFS volume to the instance.
