---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.Governance

$params = @{
	accessPackageId = "b2eba9a1-b357-42ee-83a8-336522ed6cbf"
	displayName = "Users from connected organizations can request"
	description = "Allow users from configured connected organizations to request and be approved by their sponsors"
	canExtend = $false
	durationInDays = 365
	expirationDateTime = $null
	requestorSettings = @{
		scopeType = "AllExistingConnectedOrganizationSubjects"
		acceptRequests = $true
	}
	requestApprovalSettings = @{
		isApprovalRequired = $true
		isApprovalRequiredForExtension = $false
		isRequestorJustificationRequired = $true
		approvalMode = "SingleStage"
		approvalStages = @(
			@{
				approvalStageTimeOutInDays = 14
				isApproverJustificationRequired = $true
				isEscalationEnabled = $false
				escalationTimeInMinutes = 11520
				primaryApprovers = @(
					@{
						"@odata.type" = "#microsoft.graph.groupMembers"
						isBackup = $true
						id = "d2dcb9a1-a445-42ee-83a8-476522ed6cbf"
						description = "group for users from connected organizations which have no external sponsor"
					}
					@{
						"@odata.type" = "#microsoft.graph.externalSponsors"
						isBackup = $false
					}
				)
			}
		)
	}
	questions = @(
		@{
			isRequired = $false
			text = @{
				defaultText = "what state are you from?"
				localizedTexts = @(
					@{
						text = "¿De qué estado eres?"
						languageCode = "es"
					}
				)
			}
			"@odata.type" = "#microsoft.graph.accessPackageMultipleChoiceQuestion"
			choices = @(
			)
			allowsMultipleSelection = $false
		}
		@{
			isRequired = $false
			text = @{
				defaultText = "Who is your manager?"
				localizedTexts = @(
					@{
						text = "por qué necesita acceso a este paquete"
						languageCode = "es"
					}
				)
			}
			"@odata.type" = "#microsoft.graph.accessPackageTextInputQuestion"
			isSingleLineQuestion = $false
		}
	)
}

New-MgEntitlementManagementAccessPackageAssignmentPolicy -BodyParameter $params

```