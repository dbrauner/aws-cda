# Route53 Routing Policies
* Simple
* Weighted 
* Latency
* Failover
* Geolocation

## Simple (default)
Most commonly used when you have a single resource that performs a given function for your domain, e.g. one web server that serves content for the website.

Simple routing policies are for one server.

You need a ELB to be able to point a Records set to an EC2 instance.


## weighted
* Divide the traffic in percent for example 20% to one ELB and 80% to another.
* A/B testing - new feature - helps to decrease risks in new big features.
 Splits traffic based on different weights assigned. 

The weight is not applied in single requests, you will see the division across the entire day.

(Route53 is a global service, not by region)

In the console you set the weights using a 0-255 value for each id. It will actually sum all of them and apply a rule based on that. So the sum of all of them don't need to be 100%.

If you create just one id with value 70, it will actually send 100% to it, and if you create another with same value, now they will get 50% each.

The weighted route is not a thing that will be applied to each of the users. This is a global thing, think that if you have 100 users acessing your site, the Route53 will try balance that, but this does not mean that you will access with weight. Your cache will try to access the same resource name.

