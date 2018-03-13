# What is
It uses the CloudFront Edge Locations to accelerate uploads to your S3. Instead of upload directly to S3, which can far to your location, you can use a distinct URL to upload direct to and edge location, which will then transfer that file to S3. 

e.g. douglasbrauner-s3-accelerate.amazonaws.com

The configuration is your very bucket, under Properties tab. The config has an option to compare the speed with different edge locations and normal upload. 