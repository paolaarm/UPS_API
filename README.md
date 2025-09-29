 # UPS Tracking API Workflow VSCode REST Client (Extension)

### STEPS 

1. Installing REST Client (Extension)
2. Creating ups_tracking.http file
3. REST Client Setting --> Environment Variables --> Edit in settings.json
   
   <img width="443" height="131" alt="image" src="https://github.com/user-attachments/assets/ece9e9f1-09b8-4360-853e-22ac33c04c0e" />

At the "Shared" level that is variables that will be used in both testing and production added the UPS client_id and client_secret, tracking_source, transaction_id
and Inquiry_Number (the tracking number). 

settings.json allows you to have variables for different environments. In this case I created a set of variables for the testing environment and another set of variables for 
the production environment. In reality only two variables for each. 
* UPS_BASE_URL
* access token

  

4. Back in the HTTP file created a POST request to obtain credentials 
