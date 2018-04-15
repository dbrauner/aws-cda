# For Containers
* RDS and EMR. No access to OS, only to database, no ssh. In this case, aws is responsible for patching the OS, the patlform and managing the application.


# Abstract Services
* S3, dynamoDB, Lambda. This scenario, as a customer, you are responsible for the data. The server side encryption is by aws (unless you want to send your certificates). Just the customer client-side encryption.
