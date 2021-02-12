#Exercise 10.3
##Setting up an Amazon Cloud directory
In this exercise, you will set up an Amazon Cloud Directory. Cloud Directory is a highly available multitenant directory-based store where AWS is responsible for scaling. AWS manages the directory infrastructure, while the administrators focus on building the directories and the applications that use those directories.

**Step 1: Create a Schema**
You’ll first create a schema (which defines objects in a directory) and then assign that schema to a directory. A single schema can be assigned to multiple directories, and a directory can have multiple schemas assigned to it (though typically it does not).
1.	In the AWS Services console navigation pane, under **Security, Identity & Compliance**, choose **Directory Service ➢ Schemas**.
2.	To create a custom schema based on an existing one, in the table listing the schemas, select the schema named **person**.
3.	Choose **Actions**.
4.	Choose **Download schema**.
5.	In the location where you downloaded the schema, rename the file to **test-person**.
6.	On the **Schemas** page, choose **Upload new schema**.
7.	Select *test-person* and choose **Upload**.
8.	To prevent modifications to the schema, choose **schema test-person**.
9.	Choose **Actions**.
10.	In **Major Version**, enter the identifier **1**, and choose **Publish**.
You are returned to the Schemas page. You have two versions of the test-person schema: one schema version shows versions and is listed under State as Published; the other schema version does not show versions and is listed under State as Development.
You have successfully created a schema that you will use to create a directory.

**Step 2: Create a Directory**
Before you can create a directory in Cloud Directory, Directory Service requires that you first apply a schema to it. A directory cannot be created without a schema and typically has one schema applied to it.
Create a directory that uses the schema you created in step 1.
1.	In the AWS Directory Service console navigation pane, under **Security, Identity & Compliance**, choose **Directory Service ➢ Directories**.
2.	Choose **Set up Cloud Directory**.
3.	Under **Choose a schema to apply to your new directory**, in **Cloud Directory name**, enter *test-cloud-directory*.
4.	Choose **Custom schema**.
5.	Select the custom schema named test-person with the Status of Published, and then choose **Next**.
6.	Review the directory information and make the necessary changes. When the information is correct, choose **Create**.
You have successfully created a Cloud Directory. You can modify and delete the directory, including the schema associated with the directory.
