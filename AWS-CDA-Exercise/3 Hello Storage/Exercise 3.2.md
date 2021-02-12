
# Exercise 3.2

###Upload an object to a bucket
Now that you have a bucket, you can add objects to it. In this example, you will create two objects. The first object has a text string as data, and the second object is a file. This example creates the first object by specifying the bucket name, object key, and text data directly in a call to AmazonS3Client.putObject(). The example creates a second object by using a PutObjectRequest that specifies the bucket name, object key, and file path.The PutObjectRequest also specifies the ContentType header and title metadata.

For assistance in completing this exercise, copying this code, or for code in other languages, see the following documentation:

  *https://docs.aws.amazon.com/AmazonS3/latest/dev/UploadObjSingleOpJava.html*



### 1. Enter the following code in your preferred development environment for Java:

```
import java.io.File;
import java.io.IOException;
```
```
import com.amazonaws.AmazonServiceException;
import com.amazonaws.SdkClientException;
import com.amazonaws.auth.profile.ProfileCredentialsProvider;
import com.amazonaws.services.s3.AmazonS3;
import com.amazonaws.services.s3.AmazonS3ClientBuilder;
import com.amazonaws.services.s3.model.ObjectMetadata;
import com.amazonaws.services.s3.model.PutObjectRequest;

public class UploadObject {

public static void main(String[] args) throws IOException {
String clientRegion = "*** Client region ***";
String bucketName = "*** Bucket name ***";
String stringObjKeyName = "*** String object key name ***";
String fileObjKeyName = "*** File object key name ***";
String fileName = "*** Path to file to upload ***";

try {
AmazonS3 s3Client = AmazonS3ClientBuilder.standard()
.withRegion(clientRegion)
.withCredentials(new ProfileCredentialsProvider())
.build();

// Upload a text string as a new object.
s3Client.putObject(bucketName, stringObjKeyName, "Uploaded
String Object");

// Upload a file as a new object with ContentType and title
specified.

             PutObjectRequest request = new PutObjectRequest(bucketName,
             fileObjKeyName, new File(fileName));
             ObjectMetadata metadata = new ObjectMetadata();
             metadata.setContentType("plain/text");
             metadata.addUserMetadata("x-amz-meta-title", "someTitle");
             request.setMetadata(metadata);
             s3Client.putObject(request);
       }
       catch(AmazonServiceException e) {
           // The call was transmitted successfully, but Amazon S3 couldn't
           process
          // it, so it returned an error response.
          e.printStackTrace();
      }
      catch(SdkClientException e) {
          // Amazon S3 couldn't be contacted for a response, or the client
         // couldn't parse the response from Amazon S3.
         e.printStackTrace();
       }
    }
}
```
2. Replace the static variable values for clientRegion and bucketName used in the previous exercise.

3. Replace the value for stringObjKeyName with the name of the key that you intend to create in your Amazon S3 bucket, which will upload a text string as a new object.
4. Replace the Uploaded String Object text with the text being placed inside the object that you are generating.
5. Replace the someTitle text in the code with your own metadata title for the object that you are uploading.
6. Create a local file on your machine and then replace the value for fileName with the full path and filename of the file that you created.
7. Replace the fileObjKeyName with the key name that you want for the file that you will be uploading. A file can be uploaded with a different name than the filename that’s used locally.
8. Execute the code. Your bucket gets created with the name that you specified in the region that you specified. A successful result without errors will create two objects in your bucket.
