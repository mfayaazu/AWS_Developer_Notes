#Exercise 9.1
##Launch a Sample AWS opsWorks Stacks environment
1.	Launch the **AWS Management Console**.
2.	Select **Services** ➢ **AWS OpsWorks**.
3.	Select **Add Stack**, and select **Sample stack**.
4.	Select your preferred operating system (**Linux** or **Windows**).
5.	Select **Add Instance**, and monitor the stack’s progress until it enters the online state. This deploys the app to the stack.
6.	Copy the public IP Address, and paste it into a web browser to display the sample app.
7.	Open the instance in the **AWS OpsWorks Stacks** console, and view the log entries.
8.	Verify that the Chef run was a success and which resources deploy to the instance in the log entries.
9.	Update the recipes of the automatically created layer.
10.	Remove the deploy recipe.
11.	Add a new instance to the stack and monitor its progress.
12.	Once the instance is in the online state, view the run logs to verify that the sample website is not deployed to the instance.
