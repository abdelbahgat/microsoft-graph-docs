---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.DeviceManagement.Administration

$params = @{
	"@odata.type" = "#microsoft.graph.complianceManagementPartner"
	lastHeartbeatDateTime = [System.DateTime]::Parse("2016-12-31T23:59:37.9174975-08:00")
	partnerState = "unavailable"
	displayName = "Display Name value"
	macOsOnboarded = $true
	androidOnboarded = $true
	iosOnboarded = $true
	macOsEnrollmentAssignments = @(
		@{
			"@odata.type" = "microsoft.graph.complianceManagementPartnerAssignment"
			target = @{
				"@odata.type" = "microsoft.graph.configurationManagerCollectionAssignmentTarget"
				collectionId = "Collection Id value"
			}
		}
	)
	androidEnrollmentAssignments = @(
		@{
			"@odata.type" = "microsoft.graph.complianceManagementPartnerAssignment"
			target = @{
				"@odata.type" = "microsoft.graph.configurationManagerCollectionAssignmentTarget"
				collectionId = "Collection Id value"
			}
		}
	)
	iosEnrollmentAssignments = @(
		@{
			"@odata.type" = "microsoft.graph.complianceManagementPartnerAssignment"
			target = @{
				"@odata.type" = "microsoft.graph.configurationManagerCollectionAssignmentTarget"
				collectionId = "Collection Id value"
			}
		}
	)
}

Update-MgDeviceManagementComplianceManagementPartner -ComplianceManagementPartnerId $complianceManagementPartnerId -BodyParameter $params

```