---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Teams

$params = @{
	"teamsApp@odata.bind" = "https://graph.microsoft.com/beta/appCatalogs/teamsApps/2b524e28-95ce-4c9b-9773-4a5bd6ec1770"
	consentedPermissionSet = @{
		resourceSpecificPermissions = @(
			@{
				permissionValue = "OnlineMeeting.ReadBasic.Chat"
				permissionType = "Delegated"
			}
			@{
				permissionValue = "OnlineMeetingIncomingAudio.Detect.Chat"
				permissionType = "Delegated"
			}
			@{
				permissionValue = "ChatMember.Read.Chat"
				permissionType = "Application"
			}
			@{
				permissionValue = "ChatMessage.Read.Chat"
				permissionType = "Application"
			}
		)
	}
}

New-MgChatInstalledApp -ChatId $chatId -BodyParameter $params

```