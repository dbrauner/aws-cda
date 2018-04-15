# VPC endpoints

If your instances inside the VPC, in some private subnet wants to send objects to an S3 in the public cloud, you can do that using the NAT gateway. But your instances would be acessing APIs in the public internet for that. You can send the data internally, without outside connection if you use 

You create a new role for EC2 with S3 admin access. 

You can attach an role a the EC2. 

You can ssh to the public instance and then ssh to the private instance from there.

Then you remove the NAT gateway from route tables. Now, the private instance can no longer access the S3 bucket thorught the internet. 

# Endpoint
it is in the VPC dashboard

allows you to securely connect your VPC to another service. An interface endpoint is an elastic network interface (ENI) that serves as an point for traffic destinated to the service. A gateway endpoint serves as a target for a route in your route table for traffic destinated for the service.

Then you create it selecting the service, then select the VPC and the subnet.

Now the instance in the private subnet is able to access directly the S3, not using the public subnet anymore.

