# Setting up a Static Website with S3 Bucket AWS
First create an S3 Bucket
Sign in to the AWS Management Console and open the Amazon S3 console at
https://console.aws.amazon.com/s3/.
Choose Create bucket
On the Name and region page, type a name for your bucket and choose the AWS Region where you want the bucket to reside

=> Next

=> Next

=> Next

=> Create bucket

Open the bucket Properties pane, choose Static Website Hosting.
Choose Enable website hosting.

In the Index Document box, type the name of your index document.

Write or copy the Endpoint.

Choose Save.

Adding a Bucket Policy that makes your Bucket content publicly available
In the Properties pane for the Bucket, choose Permissions.
Choose Add Bucket Policy.

Add code below and replace your-bucket-name with your bucket name

```
{
    "Version":"2012-10-17",
    "Statement":[{
        "Sid":"PublicReadForGetBucketObjects",
            "Effect":"Allow",
        "Principal": "*",
        "Action":["s3:GetObject"],
        "Resource":["arn:aws:s3:::your-bucket-name/*"
        ]
        }
    ]
}   
```     
Choose Save.

Upload your static home page to your bucket
Testing your Website
Type the Endpoint in the browser

and thats it !!