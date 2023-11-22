---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ContentApproval(
	odata_type = "#microsoft.graph.windowsUpdates.contentApproval",
	content = CatalogContent(
		odata_type = "#microsoft.graph.windowsUpdates.catalogContent",
		catalog_entry = FeatureUpdateCatalogEntry(
			odata_type = "#microsoft.graph.windowsUpdates.featureUpdateCatalogEntry",
			id = "6b7e60db-a8e4-426a-9aed-bd12b5c0b9d4",
		),
	),
	deployment_settings = DeploymentSettings(
	),
	additional_data = {
			"schedule" : {
					"start_date_time" : "String (timestamp)",
					"gradual_rollout" : {
							"@odata_type" : "#microsoft.graph.windowsUpdates.dateDrivenRolloutSettings",
							"end_date_time" : "String (timestamp)",
					},
			},
	}
)

result = await graph_client.admin.windows.updates.update_policies.by_update_policy_id('updatePolicy-id').compliance_changes.post(request_body)


```