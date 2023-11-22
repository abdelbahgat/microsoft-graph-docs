---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = TransferPostRequestBody(
	transfer_target = InvitationParticipantInfo(
		endpoint_type = EndpointType.Default,
		identity = IdentitySet(
			user = Identity(
				id = "550fae72-d251-43ec-868c-373732c2704f",
				display_name = "Heidi Steen",
				additional_data = {
						"tenant_id" : "72f988bf-86f1-41af-91ab-2d7cd011db47",
				}
			),
		),
	),
	transferee = ParticipantInfo(
		identity = IdentitySet(
			user = Identity(
				id = "751f6800-3180-414d-bd94-333364659951",
				additional_data = {
						"tenant_id" : "72f988bf-86f1-41af-91ab-2d7cd011db47",
				}
			),
		),
		participant_id = "909c6581-5130-43e9-88f3-fcb3582cde37",
	),
	additional_data = {
			"language_id" : "languageId-value",
			"region" : "region-value",
	}
)

await graph_client.communications.calls.by_call_id('call-id').transfer.post(request_body)


```