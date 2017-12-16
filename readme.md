EDGE locations are like cached servers for content delivery.

regions - geografic areas
availability zone - inside a region, you have them for contingency and redundancy.


VPC - virtual private cloud
virtual datacenter. deploy assets, connect them, 
very important - 
how to build a VPC - 

Route53 - DNS service of aws. 53 is the dns port, 
Cloud Front - content delivery network - cache assets (videos and files)

DirectConnect - connect fisical lines do AWS - directly by phone . 



COMPUTE
EC2 - elastic compute cloud - vms on aws. container services - docker containers -  ssh

Elastic BEanstalk - privision infra - 

Lambda - servless - don't log - upload code and the code responde to events.


lightsail - out-of-box cloud - 


STORAGES
S3 -

glacier - fsa - regular - 7 years - archive storage - low cost.
compliance reasons. 

EFS - elastic file service - shareble. share with multiple virtual machines.

Storage Gateway - connect s3 to your datacenter.


DATABASES:
RDS - mysql, postgresl, oracle, aurora -  

DynamoDB - non relational database. nosql - really scalable. VERY IMPORTANT

RedShift - a lot of data for reports. BI, don't run on prod database because of performance issues.

Elasticache - quicker data then from database.


MIGRATION

Snowball - move terabytes of data to cloud - send to amazon. daily rate - 

DMS - database migration service - move to other regions or redshift. its converts data as well, for example from oracle to aurora. replication and convertion.

SMS - server migration service - virtual machines - 

ANALITYCS

Athena - sql querys on files - csv, xml, json. 

EMR - big data - elastic map reduce. logs analysis - 

Cloud Search - fully managed by AWS

Elastic Search - open source framework

Kinesis - analyse market, social media data - 

