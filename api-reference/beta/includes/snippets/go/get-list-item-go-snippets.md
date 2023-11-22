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


requestParameters := &graphsites.SiteItemListItemItemItemRequestBuilderGetQueryParameters{
	Expand: [] string {"fields"},
}
configuration := &graphsites.SiteItemListItemItemItemRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

items, err := graphClient.Sites().BySiteId("site-id").Lists().ByListId("list-id").Items().ByListItemId("listItem-id").Get(context.Background(), configuration)


```