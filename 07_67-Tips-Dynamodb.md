# Conditional Writes

* DynamoDB is replicated accross 3 separated facilities, this can cause some issues! The data could be readen and writen in separated facilities. 

* if two users want to write different values to the same item at the same time, one of them can overrite the value from the other. How to prevent this? 

* A conditional write is a if/then statement in the write method, if the store value is the same as the last read value, then it writes, otherwise it will fail. 

* Conditional Writes are idempotent. This means that you can send multiple times the same conditinal write if update request, the first one will update and the others will not. For example, you want to change a price of a product by applying a discount of 10% and due a network error you don't get the response from the DynamoDB, you can then send the request again and DynamoDB will only apply the discount if the original value is the same. 

# Atomic Counters
* DynamoDB support atomic counters, where you use the *UpdateItem* operation to increment or decrement the value of an existing attribute without interfering with other requests (all write requests are applied in the order in which they were received). Example: a web application might want to maintain a counter per visitor to their site. in this case, the application would need to increment this counter regardless of its current value.

This counters are not idempotent, so they will increment everytime you call the update.

* In the exam they might ask wether you should use atomic counters or not, the answer will depend if you can rely on some error in the update and if you would need idempotent operation, in this case you need to create your own implementation with conditional writes. Is it critical that the data can not have any margin of error?

# Batch operations

* if your application needs to read multiple items, you can use the *BatchGetItem* API. A single *BatchGetItem* request can retrieve up to 1mb of data. which can contain as many as 100 items. In addition, a single BatchGetItem request can retrieve items from multiple tables. (innered tables, master/data);