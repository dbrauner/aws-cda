# Using web identity providers

* You can authenticate users using Web Identity providers (such as fb, google, amazon and any other Open-ID connect compatible identity provider). This is done using AssumeRoleWithWebIdentity API.

* But first, you need to create a role!

## steps
You authenticate with the Identity Provider (e.g. facebook) and get a token

You then request to aws with API AssumeRoleWithWebIdentity and provide the following:
1. Web Identity token 
2. App Id of provider 
3. ARN of role
Then AWS Security Token Service get you Temporary Security Credentials (15min to 1h, 1h is the default) with the following:
1. AccessKeyID;
   SecretAccessKey;
   SessionToken;
2. Expiration (TTL)
3. AssumeRoleId;
4. SubjectFromWebIdentityToken (the uniqueID that appears in an IAM policy variable for this particular identity provider)

Then you are able to access the DynamoDB.

# Setup 

* the setup can start at the 'Access Control' tab from the setting of a DynamoDB table in the AWS Console. You can choose a Web Identity provider (facebook), then select the actions, for example: BatchGetItem, PutItem, Query, etc.

The policies will show in json format with effect, action and resource (ARN of table);

* Create a new role, in Role types, you select the last: Role for Identity Provider Access, specify the web identity provider. Create role.

* Go to Create Policy then. Create your own policy and use the same policy you generated in the settings of the DynamoDB table. 

* Attach the policy to the role afterward (or you can invert the steps and create the policy first and attach it in the wizard).



