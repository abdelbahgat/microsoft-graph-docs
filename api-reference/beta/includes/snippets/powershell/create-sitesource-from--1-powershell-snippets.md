---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Compliance

$params = @{
	site = @{
		webUrl = "https://contoso.sharepoint.com/sites/HumanResources"
	}
}

New-MgBetaComplianceEdiscoveryCaseCustodianSiteSource -CaseId $caseId -CustodianId $custodianId -BodyParameter $params

```