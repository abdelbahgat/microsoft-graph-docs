---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Devices.CorporateManagement

$params = @{
	"@odata.type" = "#microsoft.graph.windowsInformationProtectionAppLockerFile"
	displayName = "Display Name value"
	fileHash = "File Hash value"
	file = [System.Text.Encoding]::ASCII.GetBytes("ZmlsZQ==")
	version = "Version value"
}

New-MgDeviceAppManagementWindowsInformationProtectionPolicyExemptAppLockerFile -WindowsInformationProtectionPolicyId $windowsInformationProtectionPolicyId -BodyParameter $params

```