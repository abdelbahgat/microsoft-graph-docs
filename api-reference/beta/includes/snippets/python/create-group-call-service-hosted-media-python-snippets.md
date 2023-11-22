---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = Call(
	odata_type = "#microsoft.graph.call",
	direction = CallDirection.Outgoing,
	subject = "Create a group call with service hosted media",
	callback_uri = "https://bot.contoso.com/callback",
	source = ParticipantInfo(
		odata_type = "#microsoft.graph.participantInfo",
		identity = IdentitySet(
			odata_type = "#microsoft.graph.identitySet",
			application = Identity(
				odata_type = "#microsoft.graph.identity",
				display_name = "TestBot",
				id = "dd3885da-f9ab-486b-bfae-85de3d445555",
			),
		),
	),
	targets = [
		InvitationParticipantInfo(
			odata_type = "#microsoft.graph.invitationParticipantInfo",
			identity = IdentitySet(
				odata_type = "#microsoft.graph.identitySet",
				user = Identity(
					odata_type = "#microsoft.graph.identity",
					display_name = "user1",
					id = "98da8a1a-1b87-452c-a713-65d3f10b5555",
				),
			),
		),
		ParticipantInfo(
			odata_type = "#microsoft.graph.participantInfo",
			identity = IdentitySet(
				odata_type = "#microsoft.graph.identitySet",
				user = Identity(
					odata_type = "#microsoft.graph.identity",
					display_name = "user2",
					id = "bf5aae9a-d11d-47a8-93b1-782504c95555",
				),
			),
		),
	],
	requested_modalities = [
		Modality.Audio,
	],
	media_config = ServiceHostedMediaConfig(
		odata_type = "#microsoft.graph.serviceHostedMediaConfig",
		remove_from_default_audio_group = False,
	),
	tenant_id = "aa67bd4c-8475-432d-bd41-39f255720e0a",
)

result = await graph_client.communications.calls.post(request_body)


```