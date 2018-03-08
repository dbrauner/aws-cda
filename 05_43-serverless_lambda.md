# hands on

Create a function - remember the supported languages: C#, go, node, python, java., php.
Use the policy for Microservices.
Create a new role for execution.

Now in the screen with the created function, you will see an IDE, which was bought by AWS, you can also set environment variables in there, and much more, like programming directly in CF.

* Remember what can trigger a function, there are a lot of events that can trigger it, but it is good to understand what can not trigger, for example an RDS and EC2, but a DynamoDB, S3 and cloudwatch can.

* Add a trigger for API gateway, after creating it, you will get the url, but invoking it would lead to an "missing authorization token" error. Clicking on "method" will lead you to a admnistration page of api gateway.

* Create a new method in Gateway for your lambda function (check proxy lambda box) - remember to deploy it afterwards.

