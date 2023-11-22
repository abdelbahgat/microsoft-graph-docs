---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.DeviceManagement.Administration

$params = @{
	"@odata.type" = "#microsoft.graph.telecomExpenseManagementPartner"
	displayName = "Display Name value"
	url = "Url value"
	appAuthorized = $true
	enabled = $true
	lastConnectionDateTime = [System.DateTime]::Parse("2016-12-31T23:58:36.6670033-08:00")
}

Update-MgDeviceManagementTelecomExpenseManagementPartner -TelecomExpenseManagementPartnerId $telecomExpenseManagementPartnerId -BodyParameter $params

```