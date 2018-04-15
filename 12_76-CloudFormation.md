# Cloud Formation

Cloud formation is free, you only pay for the resources it uses.

You take what was once a tradicional hardware infrastructure and convert it into code.

you manage and create a collection of aws resources. provisioning and updating them in predictable fashion.

Benefits is that you can apply versioning to the management, as you do for your code.

## CloudFormation Stack vs Template

Template is essentially an architectural diagram and Stack is the end result of that template, what is actually provisioned.

You create, update, delete a collection of resources by creating, updating and deleting a stack of using CloudFormation template;

they are in JSON or YAML format files.

## Elements of templates

* Mandatory - list of aws resources and their config values.
* optional - file format, version, input values for stack creation (tags, names, etc..)

* output expected - ip address, ELB address, etc. anything you would need to use the stack.

* Look up table - details of the stack

In ElasticBeanstalk you can configure your environment using a GUI, in CF you do it all by code.


# Lab
Using the console, you can create directly a stack or go to design a template.

a drag and drop screen.

There are, of course, some templates.


You can have nested template (template inside template)

in example he used a wordpress template, which specified as output the URL of the site that was generated.


you can have a look at the template that was used. and look at the parameters as well.

# Exam tips
 by default the "automatic rollback on error" is an enabled feature.

 you are charged by error! if you have a loop, you might have problems!

 you have all acess for the instances.

 you can use the condition "WaitCOndition" to make stacks wait for applications to be provisioned.

 Fn:GetAtt to define the outputs in template.

 Route53 is completed supported. IAm role is supported, you cna create A Records, Aliases and etc.


 you can provision stacks accross multiple regions! more powerful!

 ssh in RDP services as well is possible for both!

 












