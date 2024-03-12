---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.Governance

$params = @{
	catalogId = "de9315c1-272b-4905-924b-cc112ca180c7"
	accessPackageResource = @{
		displayName = "Community Outreach"
		description = "https://contoso.sharepoint.com/sites/CSR"
		resourceType = "SharePoint Online Site"
		originId = "https://contoso.sharepoint.com/sites/CSR"
		originSystem = "SharePointOnline"
		"accessPackageResourceEnvironment@odata.bind" = "accessPackageResourceEnvironments/615f2218-678f-471f-a60a-02c2f4f80c57"
	}
	requestType = "AdminAdd"
}

New-MgEntitlementManagementAccessPackageResourceRequest -BodyParameter $params

```