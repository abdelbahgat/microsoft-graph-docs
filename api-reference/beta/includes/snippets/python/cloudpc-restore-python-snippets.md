---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = RestorePostRequestBody(
	cloud_pc_snapshot_id = "A00009UV000_93aff428-61f2-467f-a879-1102af6fd4a8",
)

await graph_client.device_management.virtual_endpoint.cloud_p_cs.by_cloud_p_c_id('cloudPC-id').restore.post(request_body)


```