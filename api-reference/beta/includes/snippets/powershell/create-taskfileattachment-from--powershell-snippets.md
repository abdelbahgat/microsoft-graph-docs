---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Users

$params = @{
	"@odata.type" = "#microsoft.graph.taskFileAttachment"
	name = "smile"
	contentBytes = "a0b1c76de9f7="
	contentType = "image/gif"
}

# A UPN can also be used as -UserId.
New-MgUserTodoListTaskAttachment -UserId $userId -TodoTaskListId $todoTaskListId -TodoTaskId $todoTaskId -BodyParameter $params

```