---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc-beta communications calls transfer post --call-id {call-id} --body '{\
  "transferTarget": {\
    "@odata.type": "#microsoft.graph.invitationParticipantInfo",\
    "endpointType": "default",\
    "identity": {\
      "@odata.type": "#microsoft.graph.identitySet",\
      "user": {\
        "@odata.type": "#microsoft.graph.identity",\
        "id": "550fae72-d251-43ec-868c-373732c2704f",\
        "tenantId": "72f988bf-86f1-41af-91ab-2d7cd011db47",\
        "displayName": "Heidi Steen"\
      }\
    },\
    "languageId": "en-us",\
    "region": "amer",\
    "replacesCallId": "e5d39592-99bd-4db8-bca8-30fb894ec51d"\
  }\
}\
'

```