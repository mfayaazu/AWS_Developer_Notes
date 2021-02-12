#Exercise 4.5
##Query the items in the SQl Table

 After adding data to your SQL database, in this exercise you will be able to read or query
the items in the Users table.
 To read the items in the SQL table, run the following script:
```
 ## Exercise 4.5
 import boto3
 import json
 import datetime
 import pymysql as mariadb

 ## Variables
 rds_identifier = 'my-rds-db'
 db_name = 'mytestdb'
 user_name = 'masteruser'
 user_password = 'mymasterpassw0rd1!'
 rds_endpoint = 'my-rds-db.*****.us-east-1.rds.amazonaws.com'

 db_connection = mariadb.connect(host=rds_endpoint, user=user_name,
 password=user_password, database=db_name)
 cursor = db_connection.cursor()
 try:
     sql = "SELECT * FROM `Users`"
     cursor.execute(sql)
     query_result = cursor.fetchall()
     print('Querying the Users Table...')
     print(query_result)
 except mariadb.Error as e:
     print('Error: {}'.format(e))
     print('Sorry, something has gone wrong!')
 finally:
     db_connection.close()
```
After running the Python code, you will see the three records that you inserted in the previous exercise.
