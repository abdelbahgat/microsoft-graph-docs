---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc-beta groups create --body '{\
    "description": "Group assignable to a role",\
    "displayName": "Role assignable group",\
    "groupTypes": [\
        "Unified"\
    ],\
    "isAssignableToRole": true,\
    "mailEnabled": true,\
    "securityEnabled": true,\
    "mailNickname": "contosohelpdeskadministrators",\
    "owners@odata.bind": [\
        "https://graph.microsoft.com/beta/users/99e44b05-c10b-4e95-a523-e2732bbaba1e"\
    ],\
    "members@odata.bind": [\
        "https://graph.microsoft.com/beta/users/6ea91a8d-e32e-41a1-b7bd-d2d185eed0e0",\
        "https://graph.microsoft.com/beta/users/4562bcc8-c436-4f95-b7c0-4f8ce89dca5e"\
    ]\
}\
'

```