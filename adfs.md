Can you authenticate using Active Directory?
Yes, using SAML.

The flow is that you will authenticate to Active Directory first and then you will get the temporary security credential.

# The Flow:
User browse to enterprise url - the adfs server will authenticate the user.
as a response, the browser receive a SAML assertion representing the authenticated user.
The browser also sends this SAML assertion to AWS sign-on SAML endpoint.
it uses AssumeRoleWithSAML api to grant the temporary security credentials. and then gives a url for aws console.
bob is redirected.