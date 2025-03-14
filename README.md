AWS Resource Usage Tracking

Overview

This project provides a Bash shell script to track AWS resource usage, ensuring cost efficiency by monitoring active services. The script generates a daily report of S3 buckets, EC2 instances, Lambda functions, and IAM users.

Why Use This Script?

Cost Optimization: Avoid unnecessary AWS costs by tracking active resources.

Automated Monitoring: Run the script daily using a cron job.

Easy to Use: Requires only AWS CLI and minimal setup.

Prerequisites

Before using the script, ensure:

AWS CLI is installed and configured (aws configure).

The script has execution permissions (chmod +x aws_resource_tracker.sh).

The user has IAM permissions:

AmazonS3ReadOnlyAccess

AmazonEC2ReadOnlyAccess

AWSLambdaReadOnlyAccess

IAMReadOnlyAccess
Setup Instructions

1.Clone the repository:
git clone https://github.com/yourusername/aws-resource-tracker.git
cd aws-resource-tracker
2.Make the script executable:
chmod +x aws_resource_tracker.sh
3.Run the script manually:
./aws_resource_tracker.sh
4.View the generated report:
cat resourceTracker
Automating with Cron Job
To schedule the script to run daily at 6 AM:
1.Open crontab:
crontab -e
2.Add the following line:
0 6 * * * /path/to/aws_resource_tracker.sh
Expected Output

The script will generate a resourceTracker file containing:
Listing S3 Buckets...
2025-01-25 10:35:46 my-s3-bucket

Listing EC2 Instances...
"i-1234567890abcdef0"

Listing Lambda Functions...
{
    "Functions": []
}

Listing IAM Users...
{
    "Users": [
        {
            "UserName": "keerthi",
            "UserId": "AIDAVVZPCQNSF5N2JHQHX"
        }
    ]
}
Contributing

Feel free to submit issues or pull requests to improve this script!

