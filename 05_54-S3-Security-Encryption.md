# Security & Encryption
## Security

* By default, all newly created buckets are PRIVATE

* Access control to buckets is defined by:
	* Bucket policies - that will work for the entire bucket
	* Access Control Lists - Drill down to individual objects.

* S3 buckets can be configured to create access logs - which log all requests made to s3 bucket - the logs can be sent to another bucket/aws account.

# Encryption

There are four methods of encryption, you should now how all they work for the exam.

Two types:
* In transit - It is the encryption at level of transit, from A to B, using SSL/TLS.

* At rest - there is server side encryption and client side encryption, in the server side there are 3 different methods:
	* S3 Managed Keys - SSE-S3 - the certificates managed by aws are encrypted in their side with SHA 256 and they rotate the keys regularly.

	* AWS Key Management Service, Managed keys - SSE-KMS - pretty similar to SSE-S3,but it is a bit more powerful, it has for example auditig to see who used your keys and when. You can create new keys as well.
	* Server Side encryption with Customer Provided Keys - SSE-C you upload and manage your keys by yourself.

* Client side encryption - you encrypt your data and thats it..



