# versioning

always remember, dns is lower case.
enable versioning in bucket creation

* permissions are configured in bucket level as well by object.

once enabled for a bucket, versioning can not be removed, but it can be disabled.

if you want to remove versioning of your objects, you basically need to create another bucket and copy them to this bucket without versioning.

for a new version of a file, I can also change the access permissions of it.

Lifecycle policies are important, because each version of the file is actually a new file. Big files with a lot of versions may turn to be a problem!

## deletion
if you delete a version of an object, it is lost forever, however, if you delete the very object, you can restore it with the versions.

* initiate restore refers to glacier, not versioned files!

* to restore a file in S3, you need to go to the versions history and delete the deletion marker of the object, so the last version becames the version before the deletion.

* Once enabled, you will have deletion markers for objects, (not deletion itself); you can use MFA Delete to avoid acidental deletion of files, this makes a requirement to use multi-factor authentication to delete files, which is additional security layer.