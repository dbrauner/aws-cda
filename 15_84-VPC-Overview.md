# VPC

Amazon VPC lets you provision a logically isolated section of the Amazon WebServices where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address range, creation of subnets, and configuration of route tables and network gateways.

# VPN
 You can create a hardware virtual private network connection between your corporate datacenter and your VPC and leverage the AWS cloud as an extension of your corporate datacenter.


## Subnets

If you have a public subnet, this means you have internet connection. For private subnet you don't.

Virtual Datacenter in the cloud.


Amazon allows you to use a bunch of ip ranges:

10.0.0.0/8 

172.16.0.0/12

192.168.0.0/16

## What you can do?

* Launch instances into a subnet of your choosing
* Assign custom IP adresses ranges in each subnet
* Configure route tables between subnets
* Create internet gateway and attach it to our VPC (only one!)
* Much better security control over your aws resources (network ACL to block ip)
* instance security group - Security gropus across AZ to spam isntances
* ACL for subnet.

## Default VPC

* Default VPC is user friendly, allowing you to immediate deploy instances. 
* All subnets in default VPC have a route out to internet, they are not private by default.
* Each EC2 instance has both a public and a private IP address.

## Custom VPC
* Only private ip address for EC2.
* 

## VPC peering
you can make one VPC to talk to another via peering, it allows you to connect via a direct network route using private IP address. 
* Instances behave as they are in the same network, You can peer VPC's with other AWS accounts as well, as with others VPC in the same account.

No transitive peering, a peering made in a star configuration.

Security groups are stateful - this means that if I open port 80, it is open for inbound and outbound.
ACL are  stateless - I need to open port 80 for inbound and open it to outbound (if needed);



