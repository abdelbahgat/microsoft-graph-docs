---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc tenant-relationships delegated-admin-relationships patch --delegated-admin-relationship-id {delegatedAdminRelationship-id} --body '{\
  "displayName": "Updated Contoso admin relationship",\
  "duration": "P31D",\
  "customer": {\
    "tenantId": "52eaad04-13a2-4a2f-9ce8-93a294fadf36"\
  },\
  "accessDetails": {\
    "unifiedRoles": [\
      {\
        "roleDefinitionId": "44367163-eba1-44c3-98af-f5787879f96a"\
      },\
      {\
        "roleDefinitionId": "29232cdf-9323-42fd-ade2-1d097af3e4de"\
      },\
      {\
        "roleDefinitionId": "69091246-20e8-4a56-aa4d-066075b2a7a8"\
      },\
      {\
        "roleDefinitionId": "3a2c62db-5318-420d-8d74-23affee5d9d5"\
      }\
    ]\
  },\
  "autoExtendDuration": "P180D"\
}\
'

```