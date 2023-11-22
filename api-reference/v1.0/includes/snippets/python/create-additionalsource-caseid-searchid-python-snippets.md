---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = SiteSource(
	odata_type = "microsoft.graph.security.siteSource",
	site = Site(
		web_url = "https://contoso.sharepoint.com/sites/SecretSite",
	),
)

result = await graph_client.security.cases.ediscovery_cases.by_ediscovery_case_id('ediscoveryCase-id').searches.by_ediscovery_search_id('ediscoverySearch-id').additional_sources.post(request_body)


```