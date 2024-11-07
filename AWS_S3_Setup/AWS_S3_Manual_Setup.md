AWS S3 Manual Setup for Healthcare Appointments Project
This document provides instructions on setting up an S3 bucket to store healthcare appointment data. This includes creating the bucket, setting up permissions, and organizing data files.

Steps
Step 1: Log into the AWS Management Console
Go to the AWS Management Console.
Log in to your AWS account.
Step 2: Navigate to Amazon S3
In the AWS Management Console, search for S3 in the search bar and select S3 from the results.
This will take you to the Amazon S3 dashboard.
Step 3: Create a New S3 Bucket
In the S3 dashboard, click Create bucket.
Bucket Name: Enter a unique name for your bucket. This name must be globally unique. For example: healthcare-appointments-data.
AWS Region: Select the region closest to you or your project’s requirements (e.g., us-east-1).
Block Public Access settings for this bucket: Keep all options checked to ensure the data remains private.
Step 4: Configure Bucket Settings (Optional)
Versioning: If you want to keep multiple versions of your files, enable versioning. This is optional but can be useful for data recovery.
Tags: Add tags to help categorize and manage your bucket. Example tags:
Project: HealthcareAppointmentsAnalysis
Owner: YourName
Department: DataScience
Default encryption: Enable server-side encryption if you want additional security for your data.
Step 5: Set Permissions
Bucket Policy: To keep data secure, no public access should be enabled.
If you later need to share the data, consider setting specific IAM policies for users or roles rather than making the bucket public.
IAM Permissions:
If this bucket will be accessed by other AWS services (e.g., Snowflake), ensure the necessary IAM roles or users have s3:GetObject, s3:PutObject, and s3:ListBucket permissions.
Step 6: Create a Folder Structure for Organizing Data (Optional)
Inside your new bucket, you can create folders to organize your data. Recommended structure:
/raw_data: For storing original, unprocessed data.
/processed_data: For processed or transformed data files.
/logs: For storing logs related to data processing.
To create a folder, click on Create folder, name it, and click Save.
Step 7: Upload Data Files
Open the folder (e.g., /raw_data) where you want to upload the healthcare appointments dataset.
Click Upload and then Add files.
Select the healthcare dataset file(s) from your local system and click Open.
Click Upload to store the files in the bucket.
Step 8: Review Bucket and File Permissions
Once the files are uploaded, click on a file to verify its permissions.
Ensure the permissions are set so that only authorized users or services can access the files.
Additional Considerations
Data Lifecycle Policies (Optional)
If you want to automatically archive or delete old data, consider setting up lifecycle policies:

Go to Management tab in your bucket.
Click Create lifecycle rule.
Name the rule and add filters if necessary.
Configure the actions, such as transitioning objects to different storage classes (e.g., Glacier for archival) or setting expiration dates for deletion.
Monitoring and Logging (Optional)
For monitoring bucket usage or access patterns:

In the Properties tab, enable Server access logging to track requests made to your bucket.
Enable CloudWatch metrics to track storage and request metrics.
Summary
Your S3 bucket is now set up and configured to securely store your healthcare appointments data. Follow the steps above to maintain and monitor the data, ensuring that the required permissions are set for both security and project needs.

