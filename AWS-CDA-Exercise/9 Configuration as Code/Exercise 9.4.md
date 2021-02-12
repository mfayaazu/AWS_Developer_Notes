#Exercise 9.4
##Configure Auto healing event notifications in AWS opsWorks Stacks
1.	Launch the **Amazon SNS console**.
2.	Create a new notification topic with your email address as a recipient.
3.	Launch the **Amazon CloudWatch console**.
4.	Create an Amazon CloudWatch Rule.
a.	Edit the JSON version of the rule pattern to use:
```
    {
      "source": [ "aws.opsworks" ],
      "detail": {
        "initiated_by": [
            "auto-healing"
          ]
      }
    }
```
5.	Add the Amazon SNS topic that you created as a target.
6.	Add permissions to the Amazon SNS topic so that it can be invoked by Amazon CloudWatch Events. An example  policy  statement  is  shown  here.  Replace  the  value of the Resource block with your topic Amazon Resource Name (ARN).
```
    {
      "Version": "2008-10-17",
      "Id": "AutoHealingNotificationPolicy",
      "Statement": [{
        "Effect": "Allow",
        "Principal": {
          "Service": "events.amazonaws.com"
          },
          "Action": "sns:Publish",
          "Resource": "arn:aws:sns:REGION:ACCOUNT:MyTopic"
          }]
      }
```
7.	Create a stack and add an instance. Make sure that Auto Healing is enabled on the stack.
8.	Launch the instance.
9.	SSH or RDP into the instance.
10.	Uninstall the **AWS OpsWorks Stacks Agent**.
11.	Wait until the instance is stopped and started by AWS OpsWorks Stacks. You will receive a notification shortly after this occurs.
