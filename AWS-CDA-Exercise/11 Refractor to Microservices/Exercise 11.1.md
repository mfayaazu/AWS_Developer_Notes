#Exercise 11.1
##Create an Amazon SQS Queue, Add Messages, and Receive Messages
In this exercise, you will use the AWS SDK for Python (Boto) to create an Amazon SQS queue, and then you will put messages in the queue. Finally, you will receive messages from this queue and delete them.
1.	Make sure that you have AWS administrator credentials set up in your account.
2.	Install the AWS SDK for Python (Boto).
Refer to *https://aws.amazon.com/sdk-for-python/*.
3.	Enter the following code into your development environment for Python or the IPython shell.
This is the code that you downloaded at the beginning of the exercises.
```
# Test SQS.
import boto3
# Pretty print.
import pprint
pp = pprint.PrettyPrinter(indent=2)

# Create queue.
sqs = boto3.resource('sqs')
queue = sqs.create_queue(QueueName='test1')
print(queue.url)
# Get existing queue.
queue = sqs.get_queue_by_name(QueueName='test1')
print(queue.url)
# Get all queues.
for queue in sqs.queues.all(): print queue

# Send message.
response = queue.send_message(MessageBody='world') 
pp.pprint(response)
# Send batch.
response = queue.send_messages(Entries=[
   { 'Id': '1', 'MessageBody': 'world' },
   { 'Id': '2', 'MessageBody': 'hello' } ])
   pp.pprint(response)
# Receive and delete all messages.
for message in queue.receive_messages():
    pp.pprint(message)
    message.delete()

# Delete queue.
queue.delete()
```
4.	Run the code.
This creates a queue, sends messages to it, receives messages from it, deletes the messages, and then deletes the queue.
5.	To experiment with the queue further, remove the comment *//queue.delete()* from the last line, which deletes the queue.
6.	After you are satisfied with your changes, delete the code.
