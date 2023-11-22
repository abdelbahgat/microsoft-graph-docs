---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc identity-governance entitlement-management assignment-policies create --body '{\
    "displayName": "Sales department users",\
    "description": "All users from sales department",\
    "allowedTargetScope": "specificDirectoryUsers",\
    "specificAllowedTargets": [\
        {\
            "@odata.type": "#microsoft.graph.attributeRuleMembers",\
            "description": "Membership rule for all users from sales department",\
            "membershipRule": "(user.department -eq \"Sales\")"\
        }\
    ],\
    "automaticRequestSettings": {\
        "requestAccessForAllowedTargets": true,\
        "removeAccessWhenTargetLeavesAllowedTargets": true,\
        "gracePeriodBeforeAccessRemoval": "P7D"\
    },\
    "accessPackage": {\
        "id": "8a36831e-1527-4b2b-aff2-81259a8d8e76"\
    }\
}\
'

```