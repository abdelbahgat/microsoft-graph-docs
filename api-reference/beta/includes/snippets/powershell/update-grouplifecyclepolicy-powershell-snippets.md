---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Groups

$params = @{
	GroupLifetimeInDays = 180
	ManagedGroupTypes = "Selected"
	AlternateNotificationEmails = "admin@contoso.com"
}

Update-MgGroupLifecyclePolicy -GroupLifecyclePolicyId $groupLifecyclePolicyId -BodyParameter $params

```