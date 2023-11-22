---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = AccessReviewInstanceDecisionItemItemRequestBuilder.AccessReviewInstanceDecisionItemItemRequestBuilderGetQueryParameters(
		select = ["accessReviewId","reviewedDateTime","decision","justification","recommendation","reviewedBy","target"],
)

request_configuration = AccessReviewInstanceDecisionItemItemRequestBuilder.AccessReviewInstanceDecisionItemItemRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.identity_governance.access_reviews.definitions.by_access_review_schedule_definition_id('accessReviewScheduleDefinition-id').instances.by_access_review_instance_id('accessReviewInstance-id').stages.by_access_review_stage_id('accessReviewStage-id').decisions.by_access_review_instance_decision_item_id('accessReviewInstanceDecisionItem-id').get(request_configuration = request_configuration)


```