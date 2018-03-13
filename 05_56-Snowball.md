# types of snowballs

* Snowball : a brief case. petabyte-scale data transport solution that uses secure appliances to transfer large amounts of data in and out AWS. it adresses common problems with large scale data transfers, like network costs, low transfer time, security concerns. It has 1/5 of cost of the high speed network.

they give you the appliance, you store your data into it and then send to them to load to aws.

80 TB available in all regions. 

* Snowball Edge - very phsyically similar to snowball. it has 100 TB, it has it own compute capability. it is like a datacenter you can have locally. compute capacity offline, it even has lambda. 

* Snowmobile - Massive TRUCK - with a container in it. you can send 100PtB to it. extremmly ammount of data. 
Data center migration - 

-- 

The legacy option is the Import and Export, it is basically when you send your CDs and HDs to AWS for cloud storage. 
Snowball can import and export - with you have your data in glacier, you need first to retrieve them to a S3.