---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Groups

$params = @{
	displayName = "Myprefix_test_mysuffix"
	mailNickname = "Myprefix_test_mysuffix"
	onBehalfOfUserId = "onBehalfOfUserId-value"
}

Test-MgBetaGroupProperty -GroupId $groupId -BodyParameter $params

```