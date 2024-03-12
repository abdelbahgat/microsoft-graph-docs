---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Groups

$params = @{
	"@odata.type" = "#microsoft.outlookServices.openTypeExtension"
	extensionName = "Com.Contoso.Estimate"
	companyName = "Contoso"
	expirationDate = "2016-07-30T11:00:00.000Z"
	DealValue = 
	topPicks = @(
		"Employees only"
		"Add spouse or guest"
		"Add family"
	)
}

Update-MgGroupThreadPostExtension -GroupId $groupId -ConversationThreadId $conversationThreadId -PostId $postId -ExtensionId $extensionId -BodyParameter $params

```