# Running instance

To create and run a new instance, you need to use the `run-instance` command, with several arguments, example the `-security-group` and `-key-pair`. Remember that those parameteres must exists on your account in order the command succeed.

# Delete

to terminate an instance, the command is quite simple: `aws ec2 terminate-instances --instances-ids 'xxx'`


# important commands

$ aws ec2 describe-instances -- data from all running instances.

$ aws ec2 describe-images - this command describe ALL available images, so it would be better if you provide some search filters, otherwise you'll get thousands of results.

Remember the difference between start-instances and run-instances.