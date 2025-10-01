 # UPS Tracking API Workflow VSCode REST Client (Extension)

### STEPS 

1. Installing REST Client (Extension)
2. Creating ups_tracking.http file
3. Creating Environment Variables - REST Client Setting --> Environment Variables --> Edit in settings.json
   
   <img width="443" height="131" alt="image" src="https://github.com/user-attachments/assets/ece9e9f1-09b8-4360-853e-22ac33c04c0e" />

At the "Shared" level, that is variables that will be used in both testing and production added the UPS client_id and client_secret, tracking_source, transaction_id
and Inquiry_Number (the tracking number). 

settings.json allows you to have variables for different environments. In this case I created a set of variables for the testing environment and another set of variables for 
the production environment. In reality only a variable for each that is the Base URL.
* UPS_BASE_URL -> https://wwwcie.ups.com [Testing] ->  https://onlinetools.ups.com [Production]


4. Back in the HTTP file created a POST request to obtain credentials and named the request --> # @name response
   
<img width="415" height="170" alt="image" src="https://github.com/user-attachments/assets/de9a1dd4-af49-46d5-8305-1326d341c6b7" />


 * Utilized the same request structure to obtain Testing access token and Production access token simply by changing the environment.
 
 * Using Ctrl+Alt+E one can change the environment.
  <img width="319" height="77" alt="image" src="https://github.com/user-attachments/assets/77418b46-bd63-4bb6-9eaa-a12d8724965b" />
  
5. Saving access token in a variable.

Once the POST request returns the response, we can extract the "token_access" and save it in an environment variable.

@access_token =    {{response.response.body.$.access_token}}

[name of variable] - [from the response request and response body extract the access token and save it in "access token."]

<img width="383" height="70" alt="image" src="https://github.com/user-attachments/assets/1fbc01aa-166b-4fb7-a7f3-22fe4cca03c6" />


6. GET request
