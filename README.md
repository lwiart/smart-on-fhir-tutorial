# How to connect a SMART on FHIR app with EPIC and Cerner EHRs

*important: valid as of Oct 9, 2019. Check the EPIC and Cerner docs for up to date documentation.*

## Cerner
1. Create an account at https://code.cerner.com/developer/smart-on-fhir/apps
2. Create an app with the following params:  
  SMART launch URI: https://*your_github_id*.github.io/smart-on-fhir-tutorial/example-smart-app/launchCerner.html  
  Redirect URI: https://*your_github_id*.github.io/smart-on-fhir-tutorial/example-smart-app/  
  App Type: provider  
  Authorized: true (use OAuth2)  
  FHIR spec: DSTU2  
  Scopes: patient/DocumentReference.read, patient/Observation.read, patient/Patient.read, patient/DocumentReference.write, patient/Patient.write
3. paste the **client_id** from your newly created app in *smart-on-fhir-tutorial/example-smart-app/launchCerner.html* (search for client_id in FHIR.oauth2.authorize)
4. in your Cerner Code account, click on **Begin Testing** button and select a patient
5. the authentication will be done and you will be redirected to an HTML page that will display the patient info
The first call from Cerner code will look like:  
https://*your_github_id*.github.io/smart-on-fhir-tutorial/example-smart-app/launchCerner.html?iss=https%3A%2F%2Ffhir-ehr.sandboxcerner.com%2Fdstu2%2F0b8a0111-e8e6-4c26-a91c-5069cbc6b1ca&launch=84ca5e81-1efa-4202-88e5-dcc7934c7c35


Sources:
1. Cerner SMART on FHIR doc: http://fhir.cerner.com
2. Cerner wonderful SMART on FHIR tutorial: https://github.com/cerner/smart-on-fhir-tutorial


## EPIC

1. Create an account at https://open.epic.com/Account/LogOn
2. Go to the Open Epic Launchpad and in the **SMART on FHIR with OAuth2** section, enter the following info:  
    Patient context: pick the patient you want  
    Name of your app: give it the name you want  
    Your app's launch URL: https://*your_github_id*.github.io/smart-on-fhir-tutorial/example-smart-app/launchEpicLaunchpad.html  
    Your app's OAuth2 redirect URL: https://*your_github_id*.github.io/smart-on-fhir-tutorial/example-smart-app/  
3. paste the **client_id** from the launch pad in *smart-on-fhir-tutorial/example-smart-app/launchEpicLaunchpad.html* (search for client_id in FHIR.oauth2.authorize)
4. click the **LAUNCH APP** button
6- the authentication will be done and you will be redirected to an HTML page that will display the patient info
The first call from EPIC code should look like:  
https://*your_github_id*.github.io/smart-on-fhir-tutorial/example-smart-app/launchEpicLaunchpad.html?iss=<base url for EPIC SMART on FHIR>&launch=*launch_code_generated_by_EPIC_EHR*

Sources:
1. Open EPIC doc: https://open.epic.com/Launchpad/OAuth2Sso
2. Cerner wonderful SMART on FHIR tutorial: https://github.com/cerner/smart-on-fhir-tutorial


