# Pricing models
* On demand - A scenario where you need instances right on time, like a black friday, in which you expect to have a huge usage, but after a while it should go back to normal.
* Spot - Where you want to minimize the costs and don't want to worry about the running time, for example for genome processing, in which you choose a spot instance to run during the night and you don't have to worry about when it stops or starts, so you use an S3, for example, to persist data.
* Reserved - You have a lot of users, a big usage, but your applications does not spike a lot, so you can predict your needs, you can save some money by using this kind.
* Dedicated hosts - If you are required to not have multi tenant compute, like for processing for a government, you might need dedicated instances.

* Remember what spot is : you pay for the hour! 
** If you terminate, you pay that final hour, if AWS terminates (due the rules applied) you get that final hour for free.

D2 - Dense storage - File servers
R4 - Ram - memory optimized - Memory intense apps
M4 - General purpose - Application server (better than T2)
C4 - Compute optimzed - CPU intense apps
G2 - Graphics Intesive - Video - 3D streaming
I2 - I/O itense - NoSQL
T2 - Low cost - general purpose
F1 - Hardware acelleration - File programmable
X1 - Memory optimized - hana db
P2 - Graphics optimized - bitcoin - data mining

# EBS
* SSD GP2 - General purpose - up to 10k IOPS
* SSD IO1 - More than 10k IOPS
* HDD - Throuput opmitized - high loads, huge data, warehouse, 
* HDD - cold SC1 - Less frequent acessed - backup
* HDD Magnetic - Standard - cheap, infrenquently accessed, but can be used as boot volume, unlike SC1.
* 1 EBS to 1 EC2, if you need the same storage, use EFS.

# Labs
* Termination protection is off by default, you can change it in creation process.
* If you use an EBS as root volume for your EC2, the default is to delete this EBS when your EC2 instance is deleted, keep that in mind.
* The volumes can be encrypted, except for the root volume, for that you would need a 3-party application, like bit-locker.

* Volumes exists on EBS and snapshots in S3. - If you take a snapshot of a volume, it will store in S3.
Snapshots - point in time of EBS volumes.
They are incremental - so only changes are rewrited - the first can take some time.

# Security on Volumes
* Snapshots of volumes are encrypted by default,
* Volumes created from encrypted snapshots stay encrypted
* You can not share encrypted volumes.

# EBS x Instance Store
* your EC2 instance has it own store, which is called ephemeral storage, if your instance crashes, you will lose your data. 
* EBS backed instances can be stopped without losing data.


# Problem scenario - snapshot of RAID array
* Take an application consistency snapshot:
- Stop the writing operations;
- Flush cache to disk;

Three ways to do this:
- Freze file system;
- unmount RAID array;
- Shutdown the associated EC2 instance.

# AMIs
You can only launch an instance from an Amazon Machine Instace that is located in the same region, however you can perform a copy operation from the console to another region.

# CloudWatch
* Standard monitoring is each 5 minutes; you can change it to detailed monitoring, which is 1 minute.
* CloudWatch is for performance monitoring, unlike cloudtrail, which is for auditing.
* CW has dashbards, alarms, notifications when events occurs or thresholds are triggered. Logs ;

# Roles
* More secure than managing credentials;
* Easier to maintain;
* Can be created on demand - they are universal - the can be modified on demand.

# instance meta-data
* https://169.254.169.254/latest/meta-data/

# EFS
* Elastic file system
* Supports NFSv4 - you pay for storage used, no pre-provisioning required.
* Scalable up to peta-bytes.
* A lot of simultaneous connections
* Data stored accross AZ in a region
* Read after write consistency;


# Lambda
* Compute service where you can upload code which are lambda functions. Lambda will manage servers and provisioning accordingly the required usage from the code. 
No OS or patches, scaling, 
* You can use it as an event-driven compute service, so it will trigger lambda functions when events occurs, like s3 or dynamodb operations, 
* You can use it to respond to http requests, with Amazon API Gateway or API calls (AWS SDK).





























