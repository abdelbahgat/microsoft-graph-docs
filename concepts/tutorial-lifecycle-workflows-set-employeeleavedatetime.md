---
title: Set employeeLeaveDateTime
description: Configure the employeeLeaveDateTime property for a user object using Microsoft Graph. 
author: "FaithOmbongi"
ms.reviewer: Alexander.Filipin
ms.author: ombongifaith
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: conceptualPageType
ms.date: 12/08/2022
---

# Configure the employeeLeaveDateTime property for a user

This article describes how to configure the **employeeLeaveDateTime** attribute for a [user](/graph/api/resources/user?view=graph-rest-beta&preserve-view=true). This property can be used as a trigger for "leaver" workflows created using [Lifecycle Workflows](/graph/api/resources/identitygovernance-lifecycleworkflows-overview).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|User.Read.All and User-LifeCycleInfo.ReadWrite.All |
|Delegated (personal Microsoft account)|Not supported.|
|Application|User.Read.All and User-LifeCycleInfo.ReadWrite.All|

For delegated scenarios, the admin must also have the Global Administrator [Microsoft Entra role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

## Request

The following example shows a user who will leave on September 30, 2022 at 23:59.

# [HTTP](#tab/http)

```http
PATCH https://graph.microsoft.com/beta/users/df744d9e-2148-4922-88a8-633896c1e929

{
    "employeeLeaveDateTime": "2022-09-30T23:59:59Z"
}
```

# [PowerShell](#tab/powershell)

```powershell    
    Connect-MgGraph -Scopes "User.Read.All","User-LifeCycleInfo.ReadWrite.All"
    Select-MgProfile -Name "beta"

    $UserId = "528492ea-779a-4b59-b9a3-b3773ef6da6d"
    $employeeLeaveDateTime = "2022-09-30T23:59:59Z"
    
    Update-MgUser -UserId $UserId -EmployeeLeaveDateTime $employeeLeaveDateTime

    $User = Get-MgUser -UserId $UserId
    $User.EmployeeLeaveDateTime
 ```
---

## Next steps

- [Lifecycle Workflows API overview](/graph/api/resources/identitygovernance-lifecycleworkflows-overview)
- [How to synchronize attributes for Lifecycle workflows](/azure/active-directory/governance/how-to-lifecycle-workflow-sync-attributes)
