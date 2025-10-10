# VS CODE REST Client (Extension) Address Validation - UPS API

### STEPS 

1. Installing REST Client (Extension)
2. Creating ups-address-validation.http file
3. Creating Environment Variables - REST Client Setting --> Environment Variables --> Edit in settings.json
   <img width="680" height="413" alt="image" src="https://github.com/user-attachments/assets/33d1e39d-ef08-4daf-afa8-f3d35daa16d8" />

At the "Shared" level, that is variables that will be used in both testing and production added

* UPS_CLIENT_ID
* UPS_CLIENT_SECRET
* UPS_TRANSACTION_SRC
* UPS_TRANSACTION_ID

REQUIRED path Parameters [UPS Documentation --> https://developer.ups.com/tag/Address-Validation?loc=en_US]
* requestoption
* version

The settings.json allows you to have variables for different environments. In this case I created a set of variables for the testing environment and another set of variables for the production environment. In reality only a variable for each that is the Base URL.

UPS_BASE_URL -> https://wwwcie.ups.com [Testing] -> https://onlinetools.ups.com [Production]

Address related variables were added to the http files. 

4. Back in the HTTP file created a POST request to obtain credentials and named the request --> # @name token_response

   <img width="395" height="133" alt="image" src="https://github.com/user-attachments/assets/f2434a31-7fa1-48b9-8659-7e0c972f02ff" />

Utilized the same request structure to obtain Testing access token and Production access token simply by changing the environment.

Using Ctrl+Alt+E one can change the environment.

<img width="444" height="81" alt="image" src="https://github.com/user-attachments/assets/613323ff-4722-4c90-a90a-b1f85e9a05f0" />

5. Saving access token in a variable.
Once the POST request returns the response, we can extract the "token_access" and save it in an environment variable.

@access_token = {{response.response.body.$.access_token}}

[name of variable] - [from the response request and response body extract the access token and save it in "access token."]

This is crucial since it will be used for address validation request

6. POST TEST

NOTE: In the Customer Integration Environment, Street Level Address Validation will only produce results for addresses in New York (NY) and California (CA).

* Used a "XAVRequest" for a CA address for testing

  * REQUEST
    
    <img width="874" height="356" alt="image" src="https://github.com/user-attachments/assets/cd8940ab-ae6c-4377-826f-24dc59deb1ff" />


  * RESPONSE
    
    <img width="730" height="620" alt="image" src="https://github.com/user-attachments/assets/cdeb2a16-1ab5-4759-9eaa-b183b773fa84" />

7. POST PRODUCTION
   * REQUEST
   * This is the production request, utilizes a real address and file variables in the Request Body schema: application/json.
   * Query Parameters
     * regionalrequestindicator
     * maximumcandidatelistsize
        
   <img width="725" height="506" alt="image" src="https://github.com/user-attachments/assets/27a2d03f-9d46-4e1d-87a6-2a1184377fb9" />

   * RESPONSE
     
     <img width="632" height="611" alt="image" src="https://github.com/user-attachments/assets/4e1fd82e-25a3-48fe-94e5-d91148892b60" />

