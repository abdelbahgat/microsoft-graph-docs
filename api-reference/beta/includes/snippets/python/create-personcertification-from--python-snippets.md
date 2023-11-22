---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = PersonCertification(
	certification_id = "KB-1235466333663322",
	description = "Blackbelt in Marketing - Brand Management",
	display_name = "Marketing Blackbelt - Brand Management",
	thumbnail_url = "https://iame.io/dfhdfdfd334.jpg",
	web_url = "https://www.iame.io/blackbelt",
)

result = await graph_client.me.profile.certifications.post(request_body)


```