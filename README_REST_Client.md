# UPS Tracking API Workflow VSCode REST Client (Extension)

### STEPS 

1. Installing REST Client (Extension)
2. Creating ups_tracking.http file
3. Creating Environment Variables - REST Client Setting --> Environment Variables --> Edit in settings.json
   
   <img width="653" height="331" alt="image" src="https://github.com/user-attachments/assets/aaa1d57c-b2ad-4515-89cd-e189a9456d1b" />


At the "Shared" level, that is variables that will be used in both testing and production added 
* UPS_CLIENT_ID
* UPS_CLIENT_SECRET
* UPS_TRANSACTION_SRC
* UPS_TRANSACTION_ID

The settings.json allows you to have variables for different environments. In this case I created a set of variables for the testing environment and another set of variables for 
the production environment. In reality only a variable for each that is the Base URL.
* UPS_BASE_URL -> https://wwwcie.ups.com [Testing] ->  https://onlinetools.ups.com [Production]


4. Back in the HTTP file added an environment variable  for UPS_INQUIRY_NUMBER then created a POST request to obtain credentials and named the request --> # @name response
   
<img width="499" height="340" alt="image" src="https://github.com/user-attachments/assets/358682d9-8e51-4f6c-b2d6-7538812a49e4" />


 * Utilized the same request structure to obtain Testing access token and Production access token simply by changing the environment.
 
 * Using Ctrl+Alt+E one can change the environment.
  <img width="319" height="77" alt="image" src="https://github.com/user-attachments/assets/77418b46-bd63-4bb6-9eaa-a12d8724965b" />
  
5. Saving access token in a variable.

Once the POST request returns the response, we can extract the "token_access" and save it in an environment variable.

@access_token =    {{response.response.body.$.access_token}}

[name of variable] - [from the response request and response body extract the access token and save it in "access token."]

<img width="458" height="78" alt="image" src="https://github.com/user-attachments/assets/1a439bb1-de69-4bd7-ae5b-02f7719ed464" />



6. GET request

Created a GET request to obtain information regarding a specific shipment. 

<img width="427" height="114" alt="image" src="https://github.com/user-attachments/assets/4142934e-b5e8-4ab0-9261-46fbe0265314" />



 RESPONSE OBTAINED FOR TESTING ENVIRONMENT 

 <img width="534" height="736" alt="image" src="https://github.com/user-attachments/assets/4432a7ee-2c06-44f9-840e-6a2df606603b" />


 RESPONSE OBTAINED IN PRODUCTION ENVIRONMENT [REAL TRACKING]

 <img width="523" height="716" alt="image" src="https://github.com/user-attachments/assets/16871323-06b9-4ff2-bb28-206a78a9d1bf" />


