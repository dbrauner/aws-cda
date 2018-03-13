# Databases 101

* Relational database - rows, tables, fields. 
* Aurora, MariaDB, Postgres, Mysql, Oracle, sql server.

## Non relational

* MongoDB. DynamoDB. Document orientated table.

* Collection -> Document -> Key pair values.

* JSON format.


## Data Warehousing 

Used to query and analyze very large data sets, mostly in enterprise data. 
 * OLTP vs OLAP
 * OLTP - online transactional processing - differs from online Analitics processing in terms of the types of queries run.

 * OLTP example: 
 Order number 21202021

 Pulls up a row of data such as Name, Date, Adress to Deliver to, Delivery status.


 * OLAP 
 Analysis of large data, for example Net Profit of a product in some region, it will pull a large dataset and calculate that.

 It will calculate the cost of the product, the price it was sold, the difference between them.


## Elasticache - memcached and Redis 

# DMS
Database migration services
data type transformations, compression, parallel transfer, deals with changes in database during the migration.

It migrates from oracle database to mysql.

* RDS - OLTP

there are 6 databases. 

RedShift - OLAP for data warehousing.

