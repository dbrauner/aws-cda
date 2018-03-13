# Storage Gateway

* AWS Storage gateway is a service that connects an OP software appliance with cloud-based storage to provide seamless and secure integration between an organizations' OP IT environment and AWS storage infrastructure. The service enables you to securely store data to the aws cloud for scalable and cost-effective storage.

* The gateway is a virtual appliance, that you install in your OP infra, it will gate your data to aws storage (S3, glacier)

* You download it as a VM, and install it using a hypervisor, like Microsoft Hyper-V. It has an activation process, in which you configure you account and the storage settings.

## Four Types of Storage

* File Gateway (NFS) - flat files on S3, pdf, pictures - direct to s3.
* Volume Gateway (iSCSI) - it uses block based storage - like a Hard disc, you can use to store data from a database, OS volumes (does not goes to S3): 
	* Store Volumes 
	* Cached Volumes - it caches recent blocks and the rest goes to storage.
* Tape Gateway (VTL) - backup and archiving serivce - lifecycles policies to send them to glacier.


## File Gateway

Files are stored as objects to S3, they go with all metadata of it throught an NFS mount point. They can be managed as native S3 objects in the S3, like policies, versioning, lifecycle management, CRR.

The connection can be estabilished with Direct Connect (AWS), with creates a private securely channel for communication, the Internet and a Amazon VPC - the last is used in the scenario where you setup an Amazon Virtual Private Cloud and you want to use gateway to communicate from your private cloud (e.g. an EC2 machine) to the aws storage.

## Volume Gateway

The volume gateway interface presents your applications with disk volumes using the iSCSI block protocol. (Virtual Hard disk)
Data writen in these volumes can be asyncrhonously backed up to point-in-time snapshots of your volumes. stored as Amazon EBS.
The snapshots are compressed to minimize costs.

* Stored volumes - it takes snapshots and send them to EBS, they are incremental - the blocks goes from 1GB to 16TB.
In your infra, you will setup a iSCSI connection and the Gateway VM will present to your applications Volumes that they access, but this is an emulation, the real target will be at S3 (the EBS volumes). It back up your data to S3, so the volumes are actually created under your system (or if you provide another storage in your network) if the storage has 1TB, it will use 1TB of your infra.

* Chached Volumes - it uses the AWS storage as your primaly storage, it has the twice as much capability of stored volumes, so it can be up to 32TB. All your data is sent to AWS and the most frequently access data is cached in the gateway, so it does not uses your infrastrucutre, only for the storing the cached data.
The difference in architecture is that it basically mounts the EBS volumes on AWS side (in stored volumes they are created in the Gateway VM). it also create snapshots of your data.

## Tape Gateway

* it is a backup solution, it works with NetBackup, Backup Exec Veam, etc. You have Virtual Tapes, that are sent to S3. You need to have in place some backup strategy that stores your data in tapes. 

## Exam tips

* Files gateway - only files, direct to S3, nothing stored locally.
* Volumes gateway - all kind of data, like a hard disk. Entire dataset
* Gateway VTL - virtual Tape.

## scenarios that might come up

* You have all your data that you want to backup to AWS, you want to be able to quick analyze your data, e.g. you are an data scientist, but can't way to all your data be prepared to load, so the Stored volumes are a better alternative than Cached volumes.
* You want to have volume gateway for your data, but you can't afford to much physical space to it and you have a lot of data, you need to used cached volumes.
* You already have in place some backup service which stored data as tapes, so all you need to setup backup is to use VTL.

 






















