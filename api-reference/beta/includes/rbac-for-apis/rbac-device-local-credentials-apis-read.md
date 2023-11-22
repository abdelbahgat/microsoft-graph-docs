---
author: sandeo-MSFT
ms.topic: include
---

For delegated scenarios, the calling user must be a user assigned at least one of the following [Microsoft Entra roles](/azure/active-directory/roles/permissions-reference?toc=%2Fgraph%2Ftoc.json).

- Cloud Device Administrator
- Helpdesk Administrator
- Intune Service Administrator
- Security Administrator
- Security Reader
- Global Reader

To access the actual passwords on the device, done by including `$select=credentials` as part of the query parameters, the calling user must be a user assigned to one of the following [Microsoft Entra roles](/azure/active-directory/roles/permissions-reference?toc=%2Fgraph%2Ftoc.json).

- Cloud Device Administrator
- Intune Service Administrator
