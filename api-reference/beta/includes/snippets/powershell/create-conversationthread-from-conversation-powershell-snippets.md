---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Groups

$params = @{
	topic = "Take your wellness days and rest"
	posts = @(
		@{
			body = @{
				contentType = "html"
				content = "Waiting for the summer holidays."
			}
		}
	)
}

New-MgBetaGroupConversationThread -GroupId $groupId -ConversationId $conversationId -BodyParameter $params

```