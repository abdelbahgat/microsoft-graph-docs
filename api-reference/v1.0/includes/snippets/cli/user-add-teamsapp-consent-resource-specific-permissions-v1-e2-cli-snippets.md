---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc users teamwork installed-apps create --user-id {user-id} --body '{\
  "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps/12345678-9abc-def0-123456789a",\
  "consentedPermissionSet": {\
    "resourceSpecificPermissions": [\
      {\
        "permissionValue": "TeamsActivity.Send.User",\
        "permissionType": "Application"\
      }\
    ]\
  }\
}\
'

```