---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = Contact(
	home_address = PhysicalAddress(
		street = "123 Some street",
		city = "Seattle",
		state = "WA",
		postal_code = "98121",
	),
	birthday = "1974-07-22",
)

result = await graph_client.me.contacts.by_contact_id('contact-id').patch(request_body)


```