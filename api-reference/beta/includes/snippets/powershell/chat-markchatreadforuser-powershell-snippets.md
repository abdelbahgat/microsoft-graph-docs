---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Teams

$params = @{
	user = @{
		id = "d864e79f-a516-4d0f-9fee-0eeb4d61fdc2"
		tenantId = "2a690434-97d9-4eed-83a6-f5f13600199a"
	}
}

Invoke-MgBetaMarkChatReadForUser -ChatId $chatId -BodyParameter $params

```