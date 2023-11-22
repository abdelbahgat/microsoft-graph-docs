---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.DeviceManagement

$params = @{
	"@odata.type" = "#microsoft.graph.browserSharedCookie"
	hostOrDomain = "www.microsoft.com"
	sourceEnvironment = "InternetExplorer11"
	displayName = "Microsoft Cookie"
	hostOnly = $true
	comment = "A cookie for microsoft.com"
	path = "/"
}

New-MgBetaAdminEdgeInternetExplorerModeSiteListSharedCookie -BrowserSiteListId $browserSiteListId -BodyParameter $params

```