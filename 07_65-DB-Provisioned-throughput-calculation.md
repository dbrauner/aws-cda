# Provisioned Throughput
## Unit of Read provisioned throughput

* All reads are rounded up to increments of 4kb
* Eventually consistent reads (default) consist of 2 reads per second.
* Strongly consistent reads consist of 1 read per second.

## Unit of write provisioned throughput
* All writes are 1kb
* All write consist of 1 write per second

## The magic formula for read
Question - you have an application that requires to read 10 items of 1kb per second using eventual consistency. What should you set the read throughput to?

 *(Size of read rounded to nearest 4kb chunk / 4kb) x no of items = read throughput*
 *Divided by 2 if eventually consistent* 

Question - you have an application that requires to read 10 items of 6kb per second using eventual consitency. What should you set read throughput to ?

* Calculate how many read unit per item we need.
* 6kb rounded up to nearest increment (8kb).
* 8kb/4kb = 2 reads units per item. 

* 2 x 10 (items) = 20 units
* Using eventual consistency we get 10 units of read throughput.

It is always rounded up, if the results get you a fraction, remember that!

## Write throughput

* You have an application that requires to write 5 items, with each item being 10 kb in size per second. What should	 you set the write throughput to?

* Each write unit consist of 1kb of data. you need to write 5 items per second with each item using 10kb of data. 
* 5 x 10kb = 50 writes units
* Write throughput would be 50 units.

## Error codes
* HTTP 400 - ProvisionedThroughputExceededException
* You exceeded your maximum allowed provisioned throughput for a table or for one or more global secondary indexes.



# Question
You have a motion sensor which writes 300 items of data every 30 seconds. Each item consists of 5kb. Your application uses eventually consistent reads. What should you set the read throughput to?





# Answer

300 / 30 = 10 items per second. 5kb rounded to nearest 4kb chunk is 8kb. 8 / 4 = 2. This means you need 2 reads per item. 2 x 10 = 20 reads per second. As the reads are EVENTUALLY consistent, 20 / 2 = 10.