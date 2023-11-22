---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = Acronym(
	display_name = "DNN",
	stands_for = "Deep Neural Network",
	description = "A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers.",
	web_url = "http://microsoft.com/deep-neural-network",
	state = AnswerState.Draft,
)

result = await graph_client.search.acronyms.post(request_body)


```