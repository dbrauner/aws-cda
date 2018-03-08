# STS
It grants users a limited and temporary access to aws resources.
there are 3 types of source of users:
## Federation (typically active directory)
uses SAML - Security assertion markup language
grant temporary access based off the users active directory credentials. the interesting is that is does not need to be a user in IAM.
It also permit to log using single sign-on in AWS console without a IAM user.
## Federation with mobile app
Use Facebook, amazon, google or other openID providers to log in
Cross account Access
Lets users from other aws account to access resources 

Federation is combininig a list of users in one service to another external service. like iam and facebook.

Identity Broker is a service that will make the combination of user A to B.
Identity Store is a service that will provide the users, like amazon and facebook
Identity - a user from another service.


The basic of a STS scenario:
1) you need to develop a identity broker that will communicate with AWS STS and LDAP.
2) Identity broker will autheticate with LDAP and STS, in that order.
3) after that the token will be provided.