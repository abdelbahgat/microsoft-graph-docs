---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc-beta policies cross-tenant-access-policy default patch --body '{\
  "b2bCollaborationOutbound":\
  {\
    "usersAndGroups":\
    {\
      "accessType": "blocked",\
      "targets": [\
        {\
          "target": "0be493dc-cb56-4a53-936f-9cf64410b8b0",\
          "targetType": "group"\
        }\
      ]\
    },\
    "applications":\
    {\
      "accessType": "blocked",\
      "targets": [\
        {\
          "target": "AllApplications",\
          "targetType": "application"\
        }\
      ]\
    }\
  }\
}\
'

```