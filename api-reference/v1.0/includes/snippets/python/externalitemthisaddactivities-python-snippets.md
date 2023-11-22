---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AddActivitiesPostRequestBody(
	activities = [
		ExternalActivity(
			odata_type = "#microsoft.graph.externalConnectors.externalActivity",
			type = ExternalActivityType.Created,
			start_date_time = "2021-04-06T18:04:31.033Z",
			performed_by = Identity(
				type = IdentityType.User,
				id = "1f0c997e-99f7-43f1-8cca-086f8d42be8d",
			),
		),
	],
)

result = await graph_client.external.connections.by_external_connection_id('externalConnection-id').items.by_external_item_id('externalItem-id').microsoft_graph_external_connectors_add_activities.post(request_body)


```