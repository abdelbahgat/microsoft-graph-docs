---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.SignIns

$params = @{
	"@odata.id" = "https://graph.microsoft.com/odata/groups('1a9db3ab-0acf-4808-99ae-e8ed581cb2e0')"
}

New-MgPolicyMobileAppManagementPolicyIncludedGroupByRef -MobilityManagementPolicyId $mobilityManagementPolicyId -BodyParameter $params

```