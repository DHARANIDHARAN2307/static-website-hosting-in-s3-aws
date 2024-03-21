# static-website-hosting-in-s3-aws

Amazon Simple Storage Service (Amazon S3) serves as an object storage, offering availability of data, high scalability, performance and security to industry and wide range of customers based on their requirements. It offers different storage classes. In static website, codes are fixed until modifications are made by developers.

Architecture of diagram
![Screenshot (20)](https://github.com/DHARANIDHARAN2307/static-website-hosting-in-s3-aws/assets/113666779/8280333f-bdaf-47ac-a337-5b2ab88b111b)

### Step 1 - Create an S3 Bucket
When you first create s3 bucket
* Click on "create bucket" button.
* Provide a globally unique name for bucket and select Region.
![Screenshot_20240321_104740](https://github.com/DHARANIDHARAN2307/static-website-hosting-in-s3-aws/assets/113666779/89fec0e7-c339-4b51-b104-577e46527776)

*Disable Block all public access
![Screenshot (14)](https://github.com/DHARANIDHARAN2307/static-website-hosting-in-s3-aws/assets/113666779/95dbe58b-c3af-40c4-9983-69bb00624be2)
* Click "Create Bucket" button.
### Step 2 - Upload file
* Upload your file, index.html and error.html in s3 bucket
![Screenshot (17)](https://github.com/DHARANIDHARAN2307/static-website-hosting-in-s3-aws/assets/113666779/8fe2f96e-ae96-4dfb-a333-b9905efcf0b8)

### Step 3 - Edit the bucket policy
Click the Permissions tab to configure your bucket.
* In the permission tab, Edit the bucket policy.
* You will be able to see a blank policy editor.
* Before creating the policy,  you will need to copy the ARN of your bucket.
Add following bucket policy. Replace [YOUR_BUCKET_NAME] with name of your bucket policy.
  ```
  { 
   "Id":"Policy1",
   "Version":"2012-10-17",
   "Statement":[ 
      { 
         "Sid":"Stmt1",
         "Action":[ 
            "s3:GetObject"
         ],
         "Effect":"Allow",
         "Resource":"replace-this-string-with-your-bucket-arn/*",
         "Principal":"*"
      }
   ]
  }
  ```
Click "save" button to save changes.
![Screenshot (18)](https://github.com/DHARANIDHARAN2307/static-website-hosting-in-s3-aws/assets/113666779/1b5173c1-3449-4bcf-b653-e5080081dfa3)
### Step 4 - Enable Website Hosting
Go to Properties and enable "Static Website Hosting" option.
Note the endpoint. http://{bucket-name}.s3-website-{AWS-Region}.amazonaws.com
![Screenshot_20240321_134323](https://github.com/DHARANIDHARAN2307/static-website-hosting-in-s3-aws/assets/113666779/d618f8fb-88f0-4cfa-8e4b-021d917ddb14)
![Screenshot (19)](https://github.com/DHARANIDHARAN2307/static-website-hosting-in-s3-aws/assets/113666779/641e4f3b-f004-489d-887d-b0e00ba9cc23)










