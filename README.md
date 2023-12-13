# S3_bucket_Object_Delete
# S3 Bucket Object Deletion Script

# Overview
This Bash script is designed to facilitate the deletion of objects from an Amazon S3 bucket based on a specified date range. It employs the AWS Command Line Interface (CLI) to list and subsequently delete objects within the defined time frame.

# Usage

Ensure that you have the AWS CLI installed and configured with the necessary credentials.

Replace <s3 object uri> with the URI of your S3 object (e.g., s3://your-bucket-name/path/to/objects).

Replace <region> with the AWS region where your S3 bucket is located.

Optionally, set your preferred start date by replacing "enter preferred date" in the script with the desired date in the format "YYYY-MM-DD."

Run the script by executing the following command in your terminal:

bash
Copy code

./delete_s3_objects.sh

The script will generate a list of S3 objects within the specified date range and save it to the objects_to_delete.txt file.

Objects listed in objects_to_delete.txt will be deleted from the S3 bucket.

# Script Explanation
Calculate Date Range:

The script calculates the current date (current_date) and the end date (end_date) by subtracting 30 days from the current date.

List Objects in Date Range:

It uses the AWS CLI to list objects in the specified S3 bucket URI within the calculated date range. The output is processed using awk to filter objects based on their last modified date.

Save Objects to Delete:

The filtered objects are saved to a text file (objects_to_delete.txt). This file contains the S3 URI of objects that fall within the specified date range.

Delete Objects:

The script iterates through the list of objects in objects_to_delete.txt and uses the AWS CLI to delete each object from the S3 bucket.

# Important Note

The script does not perform any confirmation before deleting objects. Ensure that you have reviewed the objects_to_delete.txt file and are certain about the objects you intend to delete.
