#Exercise 14.7
##Create an Amazon dynamodb global Table
In this exercise, you will create a DynamoDB global table.
1.	While signed in to the AWS Management Console, open the Amazon S3 console at *https://console.aws.amazon.com/dynamodb*.
2.	Choose a region for the source table for your DynamoDB global table.
3.	In the navigation pane on the left side of the console, choose **Create Table** and then do the following:
a.	For **Table name**, type **Tables**.
b.	For **Primary key**, choose an appropriate primary key. Choose **Add sort key**, and type an appropriate sort key. The data type of both the partition key and the sort key should be strings.
4.	To create the table, choose **Create**.
This table will serve as the first replica table in a new global table, and it will be the prototype for other replica tables that you add later.
5.	Select the **Global Tables** tab, and then choose **Enable streams**. Leave the **View type** at its default value (*New and old images*).
6.	Choose **Add region**, and then choose another region where you want to deploy another replica table. In this case, choose **US West (Oregon)** and then choose **Continue**. This will start the table creation process in US West (Oregon).
The console will check to ensure that there is no table with the same name in the selected region. (If a table with the same name does exist, then you must delete the existing table before you can create a new replica table in that region.)
The **Global Table** tab for the selected table (and for any other replica tables) will show that the table is replicated in multiple regions.
7.	Add another region so that your global  table  is  replicated and  synchronized  across the United States and Europe. To do this, repeat step 6, but this time specify **EU (Frankfurt)** instead of US West (Oregon).

You have created a DynamoDB global table.
