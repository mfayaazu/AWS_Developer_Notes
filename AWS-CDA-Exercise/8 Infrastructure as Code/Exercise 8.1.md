#Exercise 8.1
##Write your own AWS Cloudformation Template
1.	Create an Amazon S3 bucket with a static website  configuration  that  includes  refer- ences to index and error documents, such as *index.html* and *error.html*, respectively.
2.	Create an output to the bucket’s website URL.
3.	Create an output that displays the bucket name.
4.	Upload the code as *index.html* to the root of the bucket for the index document.
```
      <html>
        <body>
          <h1>Hello, World!</h1>
        </body>
      </html>
```


5.	Upload the code as *error.html* to the root of the bucket for the error document.
```
      <html>
        <body>
          <h1>Oops! Something went wrong.</h1>
        </body>
      </html>
```

6.	Access the URL the output provides from your AWS CloudFormation stack to verify the static website works.
