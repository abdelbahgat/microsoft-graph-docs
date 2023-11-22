---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = MailAssessmentRequest(
	odata_type = "#microsoft.graph.mailAssessmentRequest",
	recipient_email = "tifc@a830edad9050849EQTPWBJZXODQ.onmicrosoft.com",
	expected_assessment = ThreatExpectedAssessment.Block,
	category = ThreatCategory.Spam,
	message_uri = "https://graph.microsoft.com/v1.0/users/c52ce8db-3e4b-4181-93c4-7d6b6bffaf60/messages/AAMkADU3MWUxOTU0LWNlOTEt=",
)

result = await graph_client.information_protection.threat_assessment_requests.post(request_body)


```