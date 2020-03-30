# Modernapps.ninja Course Certificate Request and Verification

Modernapps.ninja courses that offer certificates of completion and/or require completion verification should use this repository and the process described below for granting completion certificates and verifying participant records of completion. 

- For course particpants seeking to request a completion certificates, Please see section 1 below.
- For anyone seeking to verify a participants records for course completion, please see section 2 below. 

## 1.0 How to request a certificate of course completion

If you have completed a modernapps.ninja course that includes a certificate of completion, please follow the instructions below to request your certificate. 

Please note that not all courses offer a certificate of completion. All courses that include an option for a course completion certificate will provide clear instructions within the course on how to fulfill requirements and request the certificate.

If you have any questions, feedback or problems with requesting a course completion certificate, please open an issue ticket at https://github.com/modernappsninja/verify/issues

### 1.1 Request a participant repository

Please open an issue ticket at [https://github.com/modernappsninjas/home/issues](https://github.com/modernappsninjas/home/issues), select the "Request Participant Repository" template, fill in the requested details and repository will be created for you

### 1.2 Configure your participant repository

Please follow the instructions in the course you are requesting a certificate of completion for to configure your repo with the appropriate validation assets needed for your course

### 1.3 Add your record to the https://github.com/modernappsninja/verify/{Course_ID}/verify.json file for the course you completed and submit a pullrequest

Every course that offers a certificate of completion should have a subdirectory for its Course_ID on the modernappsninja/verify/{Course_ID} repository containing a verify.json file with a list of records of participants who have completed the course. 

Here is an example verify.json file:

```bash
{
    "participant":
    { "GithubUsername": "fakeGithubUsername2", "ModernappsNinjaUsername": "fakeModernAppsNinjaUsername2", "ParticipantCompletionRecordLink": "https://github.com/modernappsninjas/fakeGithubUsername1/{Course_ID}/CompletionRecord.jpg", "CompletionDate": "DDMMYYYY" },
    { "GithubUsername": "fakeGithubUsername1", "ModernappsNinjaUsername": "fakeModernAppsNinjaUsername1", "ParticipantCompletionRecordLink": "https://github.com/modernappsninjas/fakeGithubUsername1/{Course_ID}/CompletionRecord.jpg", "CompletionDate": "DDMMYYYY" }
}
```

To request a certificate of completion, add an additional record to the dataset, filling in each field with the appropriate values. Note that the example verify.json file includes the fake course ID `COU-AB-1234`, you will need to replace this value with the course number for the course you are requesting a certificate for. 

You should not need to understand json to complete this task, simply copy the first record of the dataset underneath the line that says "participant", and paste the copy of the record into the dataset, then replace the values in the record you pasted in with your own values. 

For example, if a participant with the github username "fakeGithubUsername3" wanted to request a course completion certificate for the example verify.json record above, the resulting verify.json file would be:

```bash
{
    "participant":
    { "GithubUsername": "fakeGithubUsername3", "ModernappsNinjaUsername": "fakeModernAppsNinjaUsername3", "ParticipantCompletionRecordLink": "https://github.com/modernappsninjas/fakeGithubUsername3/COU-AB-1234/CompletionRecord.jpg", "CompletionDate": "DDMMYYYY" },
    { "GithubUsername": "fakeGithubUsername2", "ModernappsNinjaUsername": "fakeModernAppsNinjaUsername2", "ParticipantCompletionRecordLink": "https://github.com/modernappsninjas/fakeGithubUsername2/COU-AB-1234/CompletionRecord.jpg", "CompletionDate": "DDMMYYYY" },
    { "GithubUsername": "fakeGithubUsername1", "ModernappsNinjaUsername": "fakeModernAppsNinjaUsername1", "ParticipantCompletionRecordLink": "https://github.com/modernappsninjas/fakeGithubUsername1/COU-AB-1234/CompletionRecord.jpg", "CompletionDate": "DDMMYYYY" }
}
```

You must provide the github username that aligns with the participant repository used to store the participant completion record. You must also provide a valid email address, please remember that this email address is exposed publicly on the internet, if you prefer you can create an account with a free email provider. 

After you submit the pull request with your update, once an authorized approver approves your request, we will submit a pullRequest to your participant repo with the certificate of completion. 

## 2.0 Verifying Participant Course Completion Records

ModernApps Ninja provides a 2-fold verification system:

1. Participants are required to post course completion records and completed assignments to their participant repository. This allows interested parties to see not only the certificate of completion, but also see the required assignment outputs that the participant created in the course. 
   - The participant record includes a CourseRecords.json file which includes links to each of the objects the participant is required to create to complete a course
   - The participant record for a given modernapps ninja Course_ID can be found at https://github.com/modernappsninjas/{ParticipantGithubID}/{Course_ID}/CourseRecords.json

2. ModernApps Ninja also provides an independent verification modality to validate the legitimacy of the records provided on the participant repository. 
   - All students who have been granted a valid certificate of completion for a modernapps ninja course will have a record in a verify.json file for each course.
   - The verify.json file for a given Course_ID can be found at https://github.com/modernappsninja/verify/{Course_ID}/verify.json
   - The modernappsninja/verify repository has restricted access to ensure that only valid records for participants who have successfully completed a course are listed in the verify.json file for the course. 