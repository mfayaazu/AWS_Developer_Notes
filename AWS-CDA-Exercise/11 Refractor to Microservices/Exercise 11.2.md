#Exercise 11.2
##Send an SMS Text Message to your Mobile phone with Amazon SnS
In this exercise, you will use Amazon SNS to publish an SMS  message to  your  mobile phone. This solution can be useful when you run a job that will take several hours to com- plete, and you do not want to wait for it to finish. Instead, you can have your app send you an SMS text message when it is done.
1.	Enter the following code into your development environment for Python or the IPython shell.
This is the code that you downloaded at the beginning of the exercises.
```
import boto3

# Create SNS client.
sns_client = boto3.client('sns')

# Send message to your mobile number.
# (Replace dummy mobile number with your number.)
sns_client.publish(
    PhoneNumber='1-222-333-3333',
    Message='Hello from your app')
```
2.	Replace the PhoneNumber value with your own number.
The 1 at the beginning is the U.S. country code, 222 is the area code, and 333-3333 is the mobile phone number.
3.	Run the code.
Check your phone to view the message.
