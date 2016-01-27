# sfmc-postman
SFMC = Salesforce Marketing Cloud

The files in this repository are to be leveraged with the Google Chrome application Postman. Postman can be installed from here: [http://www.getpostman.com/](http://www.getpostman.com)

Below are the current file descriptions.

- **SFMC.json.postman_collection**: This file needs to be imported into Postman. It hosts the actual REST and SOAP calls to the SFMC API.
- **globals.postman_globals**: This file needs to be imported into Postman. It contains the global environment variables needed to setup REST API calls. You should add variables in here that apply to all sub-environments/profiles.
- **useraccount.postman_environment**: This file needs to be imported into Postman. It contains environment variables specific to each individual SFMC account you want to access. You can clone to setup multiple SFMC accounts as needed.

### REST API Requirements
To run the REST API calls you will need to fill out at least the clientID and clientSecret variables within the userAccount environment. 

> * You must call the Auth/RequestToken REST API to get a 60 minute accessToken before making subsequent calls.

### SOAP API Requirements
You will need to fill out the soapEndPoint variable plus at least one of the following sets of variables:

- For Username/Password (WS-Security) calls soapUsername and soapPassword.
- For Token (OAuth) calls clientID and clientSecret.

> * You must call the Auth/RequestToken REST API to get a 60 minute accessToken before making subsequent token based SOAP API calls.

### Importing into Postman
You'll want to import this collection and environment variables into your instance of Postman.

To import the Collection:
![alt tag](./images/import-collection.png)

Once this is completed, you will have a new collection inside your Postman instance. 

To import an environment*:
![alt tag](./images/manage-environment.png)

* Recommendation is to edit this file *first* with your favorite editor. Don't worry about filling out every single value in the file, the import values to complete are for the keys (clientId, clientSecret)

Once you have completed both imports, you are ready to finish setting up the envrionment. In this last step, Postman will setup the rest of the needed environment variables.

First run the authentication call:

![alt tag](./images/retrieveauthtoken.png)

Second, run the Platform/Retrieve Endpoints call to inject the SOAP & Rest variables into you current environment.

![alt tag](./images/neededcalls.png)

### Additional Resources
- CODE@ App Center for creating clientId and clientSecret per SFMC business unit is here: [https://appcenter-auth.exacttargetapps.com/]()
- SOAP API end point information here: [http://help.exacttarget.com/en/technical_library/web_service_guide/working_with_soap_web_service_api/]()
- SOAP API code samples here: [http://help.exacttarget.com/en/technical_library/web_service_guide/technical_articles/]()
