# Servless

Evolution of ec2:
data center -> iaas -> paas -> containers -> serverless

PAAS - upload code, and amazon deal with all for you with elastic beanstalk.

lambda - 2015 - no containers, no paas, no iaas - just code and lambda code.

provisioning, managing servers that use to run the code. no OS, patching, scaling, in the following ways:

* it is an event-driven compute service where aws lambda will run your code in respose to events. Those events can, for example, changes in a s3-bucket or a dynamo-db table. 

* OR a compute service to run your code in response to http requests, using amazon API gateway,	or API calls with SDKs. 

* is scales out automatically, your lambda functions are automatically instanciated, you don't need to worry about.

* it works about different regions. 

## Scaling Up x Scaling out
scaling up is when you add more resources to your instance, like your database or more ram, etc. Scaling out is adding more and more instances of the same resource and make use of load balancing between those instances.

# Lambda

## Blueprint
blueprints are templates, that you can configure. 

## Trigger

you can have several different triggers for your lambda functions, like cloudwatch events, logs, codecommit, dynamodb, s3 ,sns, kinesis, aws iot, alexa, cloudfront. 

## API gateway

every time a user uses an http request with api gateway, you are invoking a new instance of lambda function. so if you have 1 million requests, you create 1 million lambda functions.

## Languages
it support many languanges, c#, java, nodejs, python. 

## princing

* charged by number of requests, but the first 1 million is free, and after that is 0.20 cents by million.

* duration: rounded by 100ms, since start of code execution to end or return, and also for amount of memory by function and GB-second. 

* No function can last more than 5 minutes! If so, you need to break your function into multiple functions.

## scaling
it scales continuously, there are no rules and configuration. 


## AMazon echo
it runs totally with lambda functions.

## serverless things

s3, api gateway, lambda, dynamodb.
now, ec2 is not serverless!

## triggers
1 event triggers 1 lambda function, but a lambda function can trigger others, so actually you have 1 - x.

if it runs complicated, you can use aws x-rays to debug and see what is happening. 

you can use it to backup a s3 to other s3 bucket in any region. it runs globally.















