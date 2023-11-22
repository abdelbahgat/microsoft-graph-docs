---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Security

$params = @{
	assignedTo = "String"
	closedDateTime = [System.DateTime]::Parse("String (timestamp)")
	comments = @(
		"String"
	)
	feedback = "@odata.type: microsoft.graph.alertFeedback"
	status = "@odata.type: microsoft.graph.alertStatus"
	tags = @(
		"String"
	)
	vendorInformation = @{
		provider = "String"
		vendor = "String"
	}
}

Update-MgBetaSecurityAlert -AlertId $alertId -BodyParameter $params

```