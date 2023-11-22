---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.DeviceManagement.Administration

$params = @{
	"@odata.type" = "#microsoft.graph.mobileThreatDefenseConnector"
	lastHeartbeatDateTime = [System.DateTime]::Parse("2016-12-31T23:59:37.9174975-08:00")
	partnerState = "available"
	androidMobileApplicationManagementEnabled = $true
	iosMobileApplicationManagementEnabled = $true
	androidEnabled = $true
	iosEnabled = $true
	windowsEnabled = $true
	androidDeviceBlockedOnMissingPartnerData = $true
	iosDeviceBlockedOnMissingPartnerData = $true
	windowsDeviceBlockedOnMissingPartnerData = $true
	partnerUnsupportedOsVersionBlocked = $true
	partnerUnresponsivenessThresholdInDays = 6
	allowPartnerToCollectIOSApplicationMetadata = $true
	allowPartnerToCollectIOSPersonalApplicationMetadata = $true
	microsoftDefenderForEndpointAttachEnabled = $true
}

Update-MgDeviceManagementMobileThreatDefenseConnector -MobileThreatDefenseConnectorId $mobileThreatDefenseConnectorId -BodyParameter $params

```