---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc policies cross-tenant-access-policy partners create --body '{\
  "tenantId": "3d0f5dec-5d3d-455c-8016-e2af1ae4d31a",\
  "b2bDirectConnectOutbound": \
  {\
    "usersAndGroups": \
    {\
      "accessType": "blocked",\
      "targets": [\
        {\
            "target": "6f546279-4da5-4b53-a095-09ea0cef9971",\
            "targetType": "group"\
        }\
      ]\
    }\
  },\
  "b2bDirectConnectInbound": \
  {\
    "applications":\
    {\
      "accessType": "allowed",\
      "targets": [\
        {\
            "target": "Office365",\
            "targetType": "application"\
        }\
      ]\
    }\
  }\
}\
'

```