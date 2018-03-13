# Query

* Query finds items in a table using only primary key attribute values. You must provide a partition attribute name and a distinct value to search for.
* You can optionally provide a sort key attribute name and value, and use a comparison operator to refine the search results.
* By default, a query returns all data (all attributes) for items with the specified primary key. However, you can use the *ProjectionExpression* parameter so that the query only returns some of the attributes, rather than all of them.

* Query results are always sorted by the sort key. If the data returns a numeric type, it will sort in numeric order, otherwise the results are sorted in ASCII code values. By default the sort way is ascending, to invert that you can set the flag *ScanIndexForward* to false.

* As it is a read, by default it will be eventually consistent, but you can change that to strongly consistent (less performance)

# Scan

* A Scan operation examines every item in the table. By default, a Scan returns all of the data attributes for every item. The same way, you can use the parameter *ProjectionExpression* to return just some attributes, rather than all of them.

## Tips

* Scan operations always scans the entire table, then filters out the values to provide the desired result. It will basically add the extra step of removing data from the result set. Avoid use of scan when possible, mainly if you are scanning large tables and then removing a lot of data from the set. As a table grows, the scan will become time costly.  The scan will examine every item from the table, so it can use all the provisioned throughput in a single operation.

* Design your tables in a way you can use the query. Get, BatchGetItems APIs instead. Alternatively, design your application to use Scan operations in a way that minimizes the impact on your table's request rate.

