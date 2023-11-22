---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Users

$params = @{
	webUrl = "https://microsoft.com"
	applicationName = "Microsoft"
	displayName = "Microsoft"
	externalId = "dk9cddce2-dce2-f9dd-e2dc-cdf9e2dccdf9"
}

# A UPN can also be used as -UserId.
New-MgBetaUserTodoListTaskLinkedResource -UserId $userId -TodoTaskListId $todoTaskListId -TodoTaskId $todoTaskId -BodyParameter $params

```