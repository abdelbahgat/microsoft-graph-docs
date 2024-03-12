---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Beta.Models.Ediscovery.NoncustodialDataSource
{
	ApplyHoldToSource = true,
	DataSource = new Microsoft.Graph.Beta.Models.Ediscovery.DataSource
	{
		OdataType = "microsoft.graph.ediscovery.userSource",
		AdditionalData = new Dictionary<string, object>
		{
			{
				"email" , "adelev@contoso.com"
			},
		},
	},
};
var result = await graphClient.Compliance.Ediscovery.Cases["{case-id}"].NoncustodialDataSources.PostAsync(requestBody);


```