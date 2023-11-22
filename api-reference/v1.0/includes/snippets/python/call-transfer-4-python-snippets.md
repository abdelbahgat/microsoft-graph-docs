---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = TransferPostRequestBody(
	transfer_target = InvitationParticipantInfo(
		odata_type = "#microsoft.graph.invitationParticipantInfo",
		identity = IdentitySet(
			odata_type = "#microsoft.graph.identitySet",
			additional_data = {
					"phone" : {
							"@odata_type" : "#microsoft.graph.identity",
							"id" : "+12345678901",
					},
			}
		),
		replaces_call_id = "e5d39592-99bd-4db8-bca8-30fb894ec51d",
		additional_data = {
				"endpoint_type" : "default",
				"language_id" : "en-us",
				"region" : "amer",
		}
	),
	additional_data = {
			"client_context" : "9e90d1c1-f61e-43e7-9f75-d420159aae08",
	}
)

await graph_client.communications.calls.by_call_id('call-id').transfer.post(request_body)


```