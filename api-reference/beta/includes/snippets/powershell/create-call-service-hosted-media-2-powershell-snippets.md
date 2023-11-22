---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.CloudCommunications

$params = @{
	"@odata.type" = "#microsoft.graph.call"
	callbackUri = "https://bot.contoso.com/callback"
	source = @{
		"@odata.type" = "#microsoft.graph.participantInfo"
		identity = @{
			"@odata.type" = "#microsoft.graph.identitySet"
			applicationInstance = @{
				"@odata.type" = "#microsoft.graph.identity"
				displayName = "Calling Bot"
				id = "3d913abb-aec0-4964-8fa6-3c6850c4f278"
			}
		}
		countryCode = $null
		endpointType = $null
		region = $null
		languageId = $null
	}
	targets = @(
		@{
			"@odata.type" = "#microsoft.graph.invitationParticipantInfo"
			identity = @{
				"@odata.type" = "#microsoft.graph.identitySet"
				phone = @{
					"@odata.type" = "#microsoft.graph.identity"
					id = "+12345678901"
				}
			}
		}
	)
	requestedModalities = @(
		"audio"
	)
	mediaConfig = @{
		"@odata.type" = "#microsoft.graph.serviceHostedMediaConfig"
	}
	tenantId = "aa67bd4c-8475-432d-bd41-39f255720e0a"
}

New-MgBetaCommunicationCall -BodyParameter $params

```