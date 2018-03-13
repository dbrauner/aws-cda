# DynamoDB

* Primary keys -> Two types of primary keys available;
* Hash key, partition key it is a Single Attribute;
* Composite - think unique ID and a data range.
  * Partition Key & sort key - Hash and range - composed of two attributes. In most common cases the sort key is the date, so you can sort the array by that as well.

## Primary keys

* Partition Key - DynamoDB uses the partition keys' value as input to an internal hash function, the output from the hash function determines the partition (this is simply the physical location in which the data is stored)
* No two items in a table can have the same partition key value. 

If you want to use the same UniqueID again, you might need to the composed type.

## Partition Key and Sort Key

* Partition Key - the same as for the last one, in this case, two items can have the same partition key, however the sort key must be different.
* All items with the same partition key are stored together, they are sorted by the sort key value.

# Indexes
* Local secondary index
 * Has the SAME partition key, but different sort key.

* Can only be created at creation time of a table - not removed or modified later on.

* Global Secondary Indexes
 * You can have different partition key and different sort key.
 * They can be created at table creation and AFTER.

# Streams
* Used to capture any kind of modification of the dynamodb tables. 
* If a new item is added to the table, the stream capture an image of the entire item, including the attributes, it is basically a snapshot of that item.
* If the item is updated, the stream captures the before and after the modification, the attributes in this case.

* If is deleted, the same as added, but before deletion.

* DynamoDB Streams stores for 24 hours. not a safe place to persist data, just temporary. It can trigger a lambda function. 


## Managing it

You can export the data to an csv directly from the dashboard.

You can set up CloudWatch metrics for it. set alarms for when some capacity changes (read and writes).

You can have up to 5 Local secondary indexes and 5 global indexes. select the primary key and sort key.

