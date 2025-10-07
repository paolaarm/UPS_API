# GOOGLE ADDRESS VALIDATION WORKFLOW VS CODE REST Client (Extension) 

### STEPS 
1. Create a project in GCP
2. Obtain API Key
3. Create a HTTP file for the workflow
4. Creating Environment Variables - REST Client Setting --> Environment Variables --> Edit in settings.json

<img width="570" height="211" alt="image" src="https://github.com/user-attachments/assets/81090ebf-5007-4711-88cc-86badb4f5ef7" />

* This step ensures the API KEY will be protected
5. Created a specific environment for Google Address Validation API Specifics 
* Only holds the Base URL as of now
  
  <img width="421" height="67" alt="image" src="https://github.com/user-attachments/assets/d7284aa4-e7ff-48d6-915b-cccde88a7558" />
  
6. Back in HTTP file created variables for the address to allow reusability in JSON body for the request.

  <img width="302" height="170" alt="image" src="https://github.com/user-attachments/assets/fdc7ac09-7434-492b-9f28-7d5e064b3cd8" />

7. POST REQUEST

   <img width="392" height="208" alt="image" src="https://github.com/user-attachments/assets/9c936e38-fee7-4081-9102-0f8ee7a9495b" />

8. Response basic JSON
   
<img width="1242" height="686" alt="image" src="https://github.com/user-attachments/assets/07f935e0-606a-4cf4-9ddc-426df527d84f" />

9. Response CASS Style JSON

<img width="1242" height="686" alt="image" src="https://github.com/user-attachments/assets/919eafb8-668f-475a-a8d5-04b7da6756d2" />

