---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



getCompatibleHubContentTypes, err := graphClient.Sites().BySiteId("site-id").Lists().ByListId("list-id").ContentTypes().GetCompatibleHubContentTypes().Get(context.Background(), nil)


```