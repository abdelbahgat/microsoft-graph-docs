---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc security attack-simulation simulations patch --simulation-id {simulation-id} --body '{\
  "@odata.etag": "\"0100aa9b-0000-0100-0000-6396fa270000\"",\
  "id": "2f5548d1-0dd8-4cc8-9de0-e0d6ec7ea3dc",\
  "displayName": "Graph Simulation",\
  "payload@odata.bind":"https://graph.microsoft.com/v1.0/security/attacksimulation/payloads/12345678-9abc-def0-123456789a",\
  "durationInDays": 7,\
  "attackTechnique": "credentialHarvesting",\
  "attackType": "social",\
  "status": "scheduled",\
  "includedAccountTarget": {\
    "@odata.type": "#microsoft.graph.addressBookAccountTargetContent",\
    "type" : "addressBook",\
    "accountTargetEmails" : [\
        "faiza@contoso.com"\
    ]\
  },\
  "excludedAccountTarget": {\
    "@odata.type": "#microsoft.graph.addressBookAccountTargetContent",\
    "type" : "addressBook",\
    "accountTargetEmails" : [\
        "sam@contoso.com"\
    ]\
  }\
}\
'

```