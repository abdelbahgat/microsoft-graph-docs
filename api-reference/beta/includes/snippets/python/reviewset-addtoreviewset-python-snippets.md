---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AddToReviewSetPostRequestBody(
	source_collection = SourceCollection(
		id = "1a9b4145d8f84e39bc45a7f68c5c5119",
	),
	additional_data = {
			"additional_data" : "linkedFiles",
	}
)

await graph_client.compliance.ediscovery.cases.by_case_id('case-id').review_sets.by_review_set_id('reviewSet-id').microsoft_graph_ediscovery_add_to_review_set.post(request_body)


```