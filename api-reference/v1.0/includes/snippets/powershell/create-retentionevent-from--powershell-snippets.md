---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Security

$params = @{
	"@odata.type" = "#microsoft.graph.security.retentionEvent"
	displayName = "String"
	description = "String"
	eventQuery = @(
		@{
			"@odata.type" = "microsoft.graph.security.eventQuery"
		}
	)
	eventTriggerDateTime = [System.DateTime]::Parse("String (timestamp)")
	"retentionEventType@odata.bind" = "https://graph.microsoft.com/v1.0/security/triggerTypes/retentionEventType/9eecef97-fb3c-4c68-825b-4dd74530863a"
}

New-MgSecurityTriggerRetentionEvent -BodyParameter $params

```