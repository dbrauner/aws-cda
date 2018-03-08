# why?

Well, price... backup and so on. 

## Lifeciclye

Quite similar to replication, the config is under the Management tab. 

The difference is that you make transition of the objects to an class Standard IA and/or to a Amazon Glacier Storage. 

As the same in the replication, you can filter objects in the lifecycle rule by prefix or even by tags.

he said that the object need to be over 128kbts to be transitioned.

Thats because the minimum size for IA is 128kbs, so if you store files smaller than this, you will be charged with the difference of this size. 

Different from replication, lifecycle is not required to have versioning on objects!

It can be applied on all versions (current and olders)

Expiration is another feature, in which you can delete the objects after they were moved, for example 425 days after it.


For example, you can use it to reduce storaging costs on S3. 
