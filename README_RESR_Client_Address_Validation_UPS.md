# VS CODE REST Client (Extension) Address Validation - UPS API

### STEPS 

1. Installing REST Client (Extension)
2. Creating ups-address-validation.http file
3. Creating Environment Variables - REST Client Setting --> Environment Variables --> Edit in settings.json
   <img width="680" height="413" alt="image" src="https://github.com/user-attachments/assets/33d1e39d-ef08-4daf-afa8-f3d35daa16d8" />

At the "Shared" level, that is variables that will be used in both testing and production added

UPS_CLIENT_ID
UPS_CLIENT_SECRET
UPS_TRANSACTION_SRC
UPS_TRANSACTION_ID

REQUIRED path Parameters [UPS Documentation --> https://developer.ups.com/tag/Address-Validation?loc=en_US]
requestoption
version

The settings.json allows you to have variables for different environments. In this case I created a set of variables for the testing environment and another set of variables for the production environment. In reality only a variable for each that is the Base URL.

UPS_BASE_URL -> https://wwwcie.ups.com [Testing] -> https://onlinetools.ups.com [Production]

UPS_INQUIRY_NUMBER was added as environment variable in the HTTP file.

