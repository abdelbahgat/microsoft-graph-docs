---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ExportPostRequestBody(
	output_name = "2020-12-06 Contoso investigation export",
	description = "Export for the Contoso investigation",
	export_options = ExportOptions.OriginalFiles | ExportOptions.FileInfo | ExportOptions.Tags,
	export_structure = ExportFileStructure.Directory,
)

await graph_client.compliance.ediscovery.cases.by_case_id('case-id').review_sets.by_review_set_id('reviewSet-id').microsoft_graph_ediscovery_export.post(request_body)


```