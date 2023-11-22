---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc identity conditional-access policies create --body '{\
    "displayName": "Block access to EXO non-trusted regions.",\
    "state": "enabled",\
    "conditions": {\
        "clientAppTypes": [\
            "all"\
        ],\
        "applications": {\
            "includeApplications": [\
                "00000002-0000-0ff1-ce00-000000000000"\
            ]\
        },\
        "users": {\
            "includeGroups": ["ba8e7ded-8b0f-4836-ba06-8ff1ecc5c8ba"]\
        },\
        "locations": {\
            "includeLocations": [\
                "198ad66e-87b3-4157-85a3-8a7b51794ee9"\
            ]\
        }\
    },\
    "grantControls": {\
        "operator": "OR",\
        "builtInControls": [\
            "block"\
        ]\
    }\
}\
'

```