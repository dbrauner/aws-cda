# ElasticBeanstalk - hands on

* With elasticbeanstalk you can deploy, monitor and scale applications quickly.
* providers developers or end users with the ability to provision application infrastructure is an almost transparent way.

* it allows you to just upload your code. your html files, your php files, zipped and it will provision for you.

* helps people that do not know aws.

* cloudformation goes way more deeper than elasticbeanstalk.

* removes infra managements, allowing applications to be deployed into infra env easily.

* focus in components and performance, not configuration and specifications.

# Key components

* applications are the high level structure  in beanstalk.
* Either your entire application is one EB app or 
* each logical component of your application.

* applications can have multiple environments (Prod, Staging, Dev, V1, V2, V1.1 or functional type (front-end and backend)) 

* Environment are either single instance or scalable.

* env are either web server env or worker env.

* application version are unique packages which represents version of apps.

* app are uploaded as bundle in zip or war.

* each app can have multiple versions (1 to M)

* app version can be deployed to env within an application.

# LAb
in 'create an app' page, you can select a Platform, which could be with some language, or docker with go, python or generic.

you select a preset, which can be low cost, highly available or custom config.

you can select some config like: storing logs to S3, select container options, enable cloudwatch logs. you rentention can be up to 10 years!

in instances you can select the instance type, select root volume, etc.

in Capacity you select the availability of it with load balancing and select scaling triggers.

Rolling updates and deployment - it says how the deployment should work, the propagation of code updates and software config updates.

You can select a policy, with percentage or fixed number of instances per time.

in security you can select the roles you will use, Ec2 key pair, etc.

in Monitoring you can set your healthcheck, and select your monitoring

in network you can select your own vpc or change lb settings

databases - you can use elasticbeanstalk database or select your own database (recommended); If you delete your elasticbeanstalk, you database won't be deleted if not provisioned by it, otherwise you will loose all data.

After you create your app, you can see that it created for example an EC2 instance (in the provisioned region). The instance will inherit the tags from the elasticbeanstalk.

remember that you can do code changes and config updates on the fly, and the strategy to apply this could be rooling, immutable, all at time, etc.

ElasticBeanstalk is a service that is free! you pay only for the resources that are being provisioned.


## support

tomca for java
http for php
http for phython
nginx for node
support for ruby
.net
java se
docker
go






