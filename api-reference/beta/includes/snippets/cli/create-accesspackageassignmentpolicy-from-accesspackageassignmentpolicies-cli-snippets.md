---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc-beta identity-governance entitlement-management access-package-assignment-policies create --body '{\
  "accessPackageId": "56ff43fd-6b05-48df-9634-956a777fce6d",\
  "displayName": "direct",\
  "description": "direct assignments by administrator",\
  "accessReviewSettings": null,\
  "requestorSettings": {\
    "scopeType": "NoSubjects",\
    "acceptRequests": true,\
    "allowedRequestors": []\
  },\
  "requestApprovalSettings": {\
    "isApprovalRequired": false,\
    "isApprovalRequiredForExtension": false,\
    "isRequestorJustificationRequired": false,\
    "approvalMode": "NoApproval",\
    "approvalStages": []\
  }\
}\
'

```