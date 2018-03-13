# What it is

* fast and flexible NoSQL database service for all applications, that need consistent, single-digit milisecond latency at any scale. It is a fully managed database and supports both document and key-value data models. Its flexible data model and reliable performance make it a great fit for mobile, web, gaming, ad-tech, IoT and many others applications.

* Stored on SSD storage
* Spread across 3 geographical distinct datacenters.

* It is replicated to other 2 locations after write operations

* There are 2 different data consistency models for it:

## Eventual Consistent reads (Default)
* Consistency across all copies of data is usually reached within a second. Repeating a read after a short time should return the updated data. (Best read performance)

## Strongly Consistent Read
* A Strongly consistent read returns a result that reflects all writes that received a sucessful response prior to the read. (not the same read performance)

# The basics

* Tables
 * Collection of items, which will be stored in json format. 

* Items
 * The itens will always have an attribute with key value UniqueID.
 * 

* Attributes
 * Attributes can be an key value pair, the value can be another set of values, and DynamoDB supports up to 35 nested json objects.

# Pricing
* Provisioned throughput Capacity
 * Write throughput $0.0065 per hour for every 10 units.
 * Read throughput $0.0065 per hour for every 50 units.
* A unit is defined by a single operation per second, so if you have 1 million read operations per day, you can calculate by:
1 million / 24 (hours) / 60 (minutes) / 60 (seconds) which is 11.6, rounded to 12, so you need 12 units capacity. With a rule of 3 you can get the price per hour you are going to pay.

* First 25 GB stored per month is free.
* Storage costs of $0.25 per GB per month after that.

* In Free tier, you get 25 reads and 35 writes capacity units for free.





