---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = RemoteAssistancePartner(
	odata_type = "#microsoft.graph.remoteAssistancePartner",
	display_name = "Display Name value",
	onboarding_url = "https://example.com/onboardingUrl/",
	onboarding_status = RemoteAssistanceOnboardingStatus.Onboarding,
	last_connection_date_time = "2016-12-31T23:58:36.6670033-08:00",
)

result = await graph_client.device_management.remote_assistance_partners.post(request_body)


```