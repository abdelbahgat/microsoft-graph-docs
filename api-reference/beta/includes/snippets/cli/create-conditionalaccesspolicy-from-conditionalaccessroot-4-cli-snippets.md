---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc-beta identity conditional-access policies create --body '{\
    "displayName": "Require MFA to EXO from non-complaint devices.",\
    "state": "enabled",\
    "conditions": {\
        "applications": {\
            "includeApplications": [\
                "00000002-0000-0ff1-ce00-000000000000"\
            ]\
        },\
        "users": {\
            "includeGroups": ["ba8e7ded-8b0f-4836-ba06-8ff1ecc5c8ba"]\
        },\
        "devices": {\
            "includeDevices": [\
                "All"\
            ],\
            "excludeDevices": [\
                "Compliant"\
            ]\
        }\
    },\
    "grantControls": {\
        "operator": "OR",\
        "builtInControls": [\
            "mfa"\
        ]\
    }\
}\
'

```