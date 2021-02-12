#Exercise 14.10
##Restoring an Amazon dynamodb Table from a backup
In this exercise, you will restore a DynamoDB table by using the backup created in the previous exercise.
1.	While signed in to the AWS Management Console, navigate to the DynamoDB console at *https://console.aws.amazon.com/dynamodb/*.
2.	In the navigation pane on the left side of the console, choose **Backups**.
3.	In the list of backups, choose the backup that you created in the previous step.
4.	Choose **Restore Backup**.
5.	Type a table name as the new table name. Confirm the backup name and other backup details. Then choose **Restore table** to start the restore process.
The table that is being restored is shown with the status *Creating*. After the restore process is finished, the status of your new table changes to *Active*.

You have performed the restoration of a DynamoDB table from a backup.
