 # UPS Tracking API Workflow VSCode REST Client (Extension)

### STEPS 

1. Installing REST Client (Extension)
2. Creating ups_tracking.http file
3. Creating Environment Variables - REST Client Setting --> Environment Variables --> Edit in settings.json
   
   <img width="443" height="131" alt="image" src="https://github.com/user-attachments/assets/ece9e9f1-09b8-4360-853e-22ac33c04c0e" />

At the "Shared" level, that is variables that will be used in both testing and production added the UPS client_id and client_secret, tracking_source, transaction_id
and Inquiry_Number (the tracking number). 

settings.json allows you to have variables for different environments. In this case I created a set of variables for the testing environment and another set of variables for 
the production environment. In reality only two variables for each. 
* UPS_BASE_URL -> https://wwwcie.ups.com [Testing] ->  https://onlinetools.ups.com [Production]
* access token -> Obtained in step 4

4. Back in the HTTP file created a POST request to obtain credentials
   
<img width="273" height="59" alt="image" src="https://github.com/user-attachments/assets/8f070001-d91e-4f70-a0ef-ba7d7d435a1f" />

* Utilized the same request structure to obtain Testing access token and Production access token simply by changing the environment.
* Using Ctrl+Alt+E one can select the environment.

  <img width="319" height="77" alt="image" src="https://github.com/user-attachments/assets/77418b46-bd63-4bb6-9eaa-a12d8724965b" />
5. Saved each token at their corresponding Environment Variables 
