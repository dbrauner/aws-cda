# crr

In order to have cross region replication, you must have versioning enabled on both buckets.

The replication is under the `Management` tab.

in replication rules, you can set a prefix for sources, which is basically a pattern for a folder name, for example.

you replicate from the origin to a destiny.

It can even be in another aws account.

You can change the storage class when replicating, for example from Standard to Standard - IA (infrequently access), which would be cheaper if you are using it as a backup device.

You can create a new role for this. PLEASE DO THIS! if you try to create an role with policies by yourself (or assign an existing one) you might run into errors in replication, which are not easily troubleshooted.


After enabled the replication, ONLY NEW objects will be replicated (old data not).

# aws cli for windows

You need to create a role (if not existing) and create a user with access type set to 'programatic access' (AWS CLI, SDK, API) which is different from the Aws management console access, which is basically a user with password. the first one would use a access key ID and secret access key to log in.

after creating the user you assign the role. 

by typing `aws configure` you need to provide the access key id, secret, region, etc.

## Copy using the cli
if you copy files across buckets, using for example the command: `aws s3 cp --recursive s3://origin s3://destin` it would apply the policies from the bucket, so if the destin bucket as private access to files as default and the source is public, it will apply private access to files.

## operations in replicated objects
If you delete an object in s3 source, it will replicate the deletion to the other bucket, which actually means that the object on both buckets will get an deletion marker on it. However, any change in versioning files, for example if you delete the deletion marker on the source (to restore the file) it will not replicate that action on the destin bucket. So, any changes in the object is replicated, but changes in versioning entries will not.

Cross region replication is what it says, so it is not possible to replicate to the same region!


You can't replicate to multiple bucket, would it be multiple at time or chained replicated.
HOWEVER - you can replicate prefixes for buckets. Either you replicate the whole bucket to another or via prefixed to specific buckets.


