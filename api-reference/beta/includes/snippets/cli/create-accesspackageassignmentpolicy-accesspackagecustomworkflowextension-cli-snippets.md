---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc-beta identity-governance entitlement-management access-package-assignment-policies create --body '{\
  "displayName": "extension-policy",\
  "description": "test",\
  "accessPackageId": "ba5807c7-2aa9-4c8a-907e-4a17ee587500",\
  "expiration": {\
    "type": "afterDuration",\
    "duration": "P365D"\
  },\
  "canExtend": false,\
  "requestApprovalSettings": null,\
  "requestorSettings": {\
    "acceptRequests": true,\
    "scopeType": "AllExistingDirectorySubjects",\
    "allowedRequestors": [],\
    "isOnBehalfAllowed": false\
  },\
  "accessReviewSettings": null,\
  "questions": [],\
  "customExtensionStageSettings": [\
    {\
      "stage": "assignmentRequestCreated",\
      "customExtension": {\
        "id": "219f57b6-7983-45a1-be01-2c228b7a43f8"\
      }\
    },\
    {\
      "stage": "assignmentRequestGranted",\
      "customExtension": {\
        "id": "219f57b6-7983-45a1-be01-2c228b7a43f8"\
      }\
    }\
  ]\
}\
'

```