---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc device-management role-definitions patch --role-definition-id {roleDefinition-id} --body '{\
  "@odata.type": "#microsoft.graph.roleDefinition",\
  "displayName": "Display Name value",\
  "description": "Description value",\
  "rolePermissions": [\
    {\
      "@odata.type": "microsoft.graph.rolePermission",\
      "resourceActions": [\
        {\
          "@odata.type": "microsoft.graph.resourceAction",\
          "allowedResourceActions": [\
            "Allowed Resource Actions value"\
          ],\
          "notAllowedResourceActions": [\
            "Not Allowed Resource Actions value"\
          ]\
        }\
      ]\
    }\
  ],\
  "isBuiltIn": true\
}\
'

```