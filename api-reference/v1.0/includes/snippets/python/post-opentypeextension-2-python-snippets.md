---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = OpenTypeExtension(
	odata_type = "microsoft.graph.openTypeExtension",
	extension_name = "Com.Contoso.Referral",
	additional_data = {
			"company_name" : "Wingtip Toys",
			"deal_value" : 500050,
			"expiration_date" : "2015-12-03T10:00:00.000Z",
	}
)

result = await graph_client.me.messages.by_message_id('message-id').extensions.post(request_body)


```