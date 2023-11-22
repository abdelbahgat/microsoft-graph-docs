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
			user = Identity(
				odata_type = "#microsoft.graph.identity",
				id = "550fae72-d251-43ec-868c-373732c2704f",
				display_name = "Heidi Steen",
			),
		),
		replaces_call_id = "e5d39592-99bd-4db8-bca8-30fb894ec51d",
		additional_data = {
				"endpoint_type" : "default",
		}
	),
)

await graph_client.communications.calls.by_call_id('call-id').transfer.post(request_body)


```