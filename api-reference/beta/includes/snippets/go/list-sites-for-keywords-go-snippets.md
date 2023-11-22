---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphsites "github.com/microsoftgraph/msgraph-beta-sdk-go/sites"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



requestFilter := "siteCollection/root ne null"

requestParameters := &graphsites.SitesRequestBuilderGetQueryParameters{
	Select: [] string {"siteCollection","webUrl"},
	Filter: &requestFilter,
}
configuration := &graphsites.SitesRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

sites, err := graphClient.Sites().Get(context.Background(), configuration)


```