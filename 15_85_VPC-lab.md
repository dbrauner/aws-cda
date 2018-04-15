# VPC lab
When you create a VPC, you can specify a "tenancy" as dedicated, which means that you VPC will run a dedicated hardware.

When you create a new VPC, it will create a default security group, network ACL, route table, internet gateway.

When you create a subnet, it will be delivered to a AZ, so make sure to make this explicity.

If you create a subnet with 256 ranges, which means you used: 10.0.1.0/24 - you will have 251 addresses (minus 5)

the first is reserved to network address
next 3 to amazon - (VPC router, DNS server and reserved)
last one is for broadcast.


Remember: 

you access the **Router** -> **route table** -> **Network ACL** -> **Security Group** -> **Subnet**


To make a subnet a public subnet you must do the following:
Create a Internet Gateway

Create a new Route table
Edit the routes of that and add 0.0.0.0/0 and select the internet gateway

Now all subnets associated to that route will be public accessible.

If you want to make it ipv6 enabled as well, you need to add ::/0 .


Now, when you create a new instance, your VPC will appear in Network selection, as well your subnet selection.

You must enable auto-assign public IP address in VPC configuration, otherwise this option will not appear in the EC2 instatiation, you would need to do it mannually.

In the security group selection, you will not be able to select VPC security group, only the default and new ones will appear here.


# Security Group

I can make a private subnet acessible by creating a security group for the instance which allows inbound communication.

Then I can access it, but it will not be able to access the internet from it..



# NAT instance

You can launch an NAT instance (EC2) that will route in and out traffic which will allow my private instances to access the internet.

	
# NAT Gateway

When creating a NAT gateway, you select your public subnet, select an elastic ip addreess. You can edit route table, but the gateway take some times to the booted.


Then you go the edit your route tables, and edit the default route table. If you have a deleted nat instance associated to a route, it will appear status as "black hole" =)

add 0.0.0.0/0 - and this nat gateway.

READ the COMPARISON of NAT INSTANCE and NAT GATEWAY

Availability - you should have one gateway nat for each AZ, then you have zone independent architecture.

Maintenance - gateway managed by AWS.

Bastion server - only for nat instance.


## EXAM Tips on NAT instances
* When creating a NAT instance - disable source/destination check on the instance. - this is because a nat instance is a client and server, and ec2 instances are by default forced to be only of them..
* Nat instance must be on a public subnet.
* There must be a route out of the private subnet to the NAT instance, in order to this work.
* The amount of traffic that NAt instance can support depends on the instance size. scalability is by your own! 
* they are behind a security group!

## EXAM Tips on NAT gateway
* preferred by enterprizes
* scale automatically up to 10GBps
* No need to patch
* Not associated to a security group
* Autommaticaly assigned a public ip addres
* rembember to update route tables
* use to multiple az, - for redundantion - 
* More secure - no ssh access, no antivurs, managed by aws.




