# logged in
run updates in security groups by executing yum update

To create a simple static web server, you can rely directly on the vm:

install httpd
```sh
yum install httpd -y
```

Create a simple index page:
 ```cd /var/www/html/```

 Create index.html in it:
 ```html
 <html>
<h1> Hello Cloud Gurus!</h1>
</html>

System Status Check and Instance Status Check

Different things, one is for AWS iaaS, Instace is OS.

# EBS
Root volumes can not be ecrypted of DEFAULT AMI. You can use bit locker. New volumes can be ecrypted or if you create your own AMI.

Default is to delete the EBS volume when the EC2 is deleted. Also, the termination protection is disabled by default.

# Security Groups

Any change at security groups, rules etc, it applies instantly. No waiting time. Does apply immediately
Security Groups are STATEFUL. by adding inbound rule, it adds a outbound rule. 

You can't just DENY someone or something, everything is disabled by default, so you just allow what you need.

You can create security groups and assign them to multiple EC2 instaces.
Network access control is the way to create STATELESS traffic.
Network accesss control list is useful to block specific ip addresses as well.

# Volumes
You can not have a instance of EC2 in a Availability Zone and the EB2 on another availability Zone. They are like hard-disk drives, so they have to stick together.
in volumes section, you can tell what is the root volume by looking the one with snapshot name in it.

Create snapshot of the volume. 
Copy of snapshot allow you to move it to another region.
Then you can create an image from it and you have it in another region.

# AMI

Create an image from a running instance, or you can do the other way via the EBS snapshot.

