---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc-beta organization patch --organization-id {organization-id} --body '{\
  "marketingNotificationEmails" : ["marketing@contoso.com"],\
  "onPremisesSyncEnabled" : true,\
  "privacyProfile" :\
    {\
      "contactEmail":"alice@contoso.com",\
      "statementUrl":"https://contoso.com/privacyStatement"\
    },\
  "securityComplianceNotificationMails" : ["security@contoso.com"],\
  "securityComplianceNotificationPhones" : ["(123) 456-7890"],\
  "technicalNotificationMails" : ["tech@contoso.com"]\
}\
'

```