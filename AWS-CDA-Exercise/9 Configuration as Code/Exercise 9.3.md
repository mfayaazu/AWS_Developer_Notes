#Exercise 9.3
##Migrate an Amazon rdS database
1.	Launch the **Amazon RDS console**.
2.	Create a new database instance.
3.	Connect to your database and create a user with a password. For example, to create a user with full privileges on MySQL, use the following command:
*GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'password';*
4.	Launch the **AWS OpsWorks console**.
5.	Create two stacks (one “A” stack and one “B” stack). For ease of use, try the sample Linux stack with a Node.js app.
6.	Register the RDS database instance that you created with stack A, providing the data- base username and password you created.
7.	Edit the stack’s app to include **Amazon RDS** as a data source. Select the database you registered and provide the database name.
8.	Verify that you can connect to your database by creating a simple recipe to output the credentials. Specifically, try to output to the database field of the deploy attri- butes.
9.	Run this recipe to verify that the connection information passes to your nodes.
10.	Pass the same connection information into stack A using custom JSON.
11.	**Deregister** the database from stack A and **register** it with stack B.
12.	Perform the same tasks to verify that connection details pass to the instances in stack B.
13.	Remove the custom JSON from stack A to complete the migration.
