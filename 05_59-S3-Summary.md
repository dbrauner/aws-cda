# Exam tips

* S3 is object based i.e. allows you to upload files, not databases, not file systems.
* Each file can be from 0bytes up to 5TB.
* Unlimited storage.
* Files stored in buckets - like folders, universal names! Must unique globally.
* Read after write consistency - PUTS are available imediatly after command. 
* eventual consistency for overwrite and delete - can take some times to propagate!


## S3 storage classes
* S3 - durable, imediatly available, frequently accessed. 99.99999%  eleven 9.
* S3 IA - all the same, infrequently acessed, 
* S3 RRD - reduced redudancy storage - used for generated data, that can be generated again. 99.99% only. no use mission critical data. 
* Glacier - cheapest of all - archived data - 3 to 5 hours to access.

## Core
* Key (name)
*  Value (data)
* Version Id
* Metadata
* Access Control lists

* Stores all versioning - you paid for each version of the object (each version has their own size). Great backup tool. You can delete the deletion mark, which will make the latest version available.

* Versioning can not be disabled, only suspended. Ony by recreating the bucket. 
* Versioning can use MFA on delete. additional layer of security.

* Cross region replication - used only for across regions, versioning must be enabled on both sides.

## Lifecycle

* Don't depend on versioning.
* Can be applied to all verison
* Can transit to S3 IA and then to Glacier. minimum 128kbts to IA.
* Can create rules to delete files.

## Cloud Front

* It uses Edgelocations - separated from any region/AZ>
* Origin can be S3, EC2, ELB, Route 53.
* Distribution - The name given to the CDN, which is a set of edge locations. 
	* Web distributions - websites and RTMP - media files.

* they are read and write 
* TTL is time to live - can be configured on files or on requests.

## CORS
* Need to enable it on the resource bucket and state the URL of the origin that will be calling the bucket, this is configured in XML format. Use S3 site URL and not the S3 bucket URL. It always will have s3-website.<region>.amazonaws.com in the middle.

* Multipart upload makes it easy to upload to S3.






















