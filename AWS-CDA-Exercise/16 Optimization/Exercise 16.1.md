#Exercise 16.1
##Set up a Cpu usage Alarm using AWS Cli
In this exercise, you will use the AWS CLI to create a CPU usage alarm that sends an email message using Amazon SNS when the CPU usage exceeds 70 percent.
1.	Set up an SNS topic with the name **myHighCpuAlarm** and subscribe to it. For more information, see this article: *https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/US_SetupSNS.html*
2.	Create an alarm using the *put-metric-alarm* command as follows:
```
      aws cloudwatch put-metric-alarm \
          --alarm-name cpu-mon \
          --alarm-description "Alarm when CPU exceeds 70%" \
          --metric-name CPUUtilization \
          --namespace AWS/EC2 \
          -–statistic Average \
          --period 300 \
          --threshold 70 \
          --comparison-operator GreaterThanThreshold \
          --dimensions Name=InstanceId,Value=i-12345678 \
          --evaluation-periods 2 \
          --alarm-actions arn:aws:sns:us-east-1:111122223333:myHighCpuAlarm \
          --unit Percent
```
3.	Test the alarm by forcing an alarm state change using the *set-alarm-state*
command.
a.	Change the alarm state from *INSUFFICIENT_DATA* to *OK*.
```
aws cloudwatch set-alarm-state --alarm-name cpu-mon --state-reason "initializing" --state-value OK
```
b.	Change the alarm state from *OK* to *ALARM*.
```
aws cloudwatch set-alarm-state –alarm-name cpu-mon --state-reason "initializing" --state-value ALARM
```
c.	Check that you have received an email notification about the alarm.

Using AWS CLI, you created a CPU alarm that sends an email notification when CPU usage exceeds 70 percent. You tested it by manually changing its alarm state to *ALARM*.
