---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.DeviceManagement.VirtualEndpoint.CloudPCs["{cloudPC-id}"].GetAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.Select = new string []{ "id","displayName","imageDisplayName","lastModifiedDateTime","lastRemoteActionResult","lastLoginResult","connectivityResult" };
});


```