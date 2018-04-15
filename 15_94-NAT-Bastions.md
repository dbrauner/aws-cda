# NAT x Bastion

NAT instance is created under a certain subnet in order to make internet traffic with instances that are in a private subnet in the same VPC. 

For administration purposes, you can use a Bastion web service, which is basically an instance that is in your public subnet and you use it to be able to access your private subnet instances using ssh. So, you ssh to your bastion server and then connect to the instance which is in the private subnet.

# How to make a bastion instance Higly available?

First, in case of highly availability scenarios, you'll need multiple subnets, at least two public sbnet. One subnet is always equal to one AZ. you can have a bastion in each of the subnets, so you can administrate your private instances. 
You can use autoscaling groups to define minimum of 1 bastion so if you host goes down you the autoscaling can deploy an instance in some of the AZ. You can use Route 53 with health checks on that bastion server.

Nat gateway the AWS will do the failover control for you.

# Exam tips

NAT is used to provide internet traffic to ec2 instances in the private subnets.
Bastion is used to admin. jump boxes! 

