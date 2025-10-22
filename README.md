# assessment1
# CLOUDLAUNCH
s3 BUCKET (task1)
 Created three buckets
       cloudlaaunch-bucket
       cloudlaunch-private-bucket
       cloudlaunch-visible-bucket-only

# S3 STATIC SITE LINK
 http://cloudlauch-bucket.s3-website.us-east-2.amazonaws.com

# CLOUDFront URL
https://d295p8973yh0yn.cloudfront.net/

# JSON policy attached to the IAM user
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "ListAllBuckets",
			"Effect": "Allow",
			"Action": "s3:ListBucket",
			"Resource": [
				"arn:aws:s3:::cloudlauch-bucket",
				"arn:aws:s3:::cloudlaunch-private-bucket470147111206",
				"arn:aws:s3:::cloudlaunch-visible-only-bucket470147111206"
			]
		},
		{
			"Sid": "SiteBucketReadOnly",
			"Effect": "Allow",
			"Action": "s3:GetObject",
			"Resource": "arn:aws:s3:::cloudlauch-bucket/*"
		},
		{
			"Sid": "PrivateBucketReadWrite",
			"Effect": "Allow",
			"Action": [
				"s3:GetObject",
				"s3:PutObject"
			],
			"Resource": "arn:aws:s3:::cloudlaunch-private-bucket470147111206/*"
		}
	]
}

  
   
