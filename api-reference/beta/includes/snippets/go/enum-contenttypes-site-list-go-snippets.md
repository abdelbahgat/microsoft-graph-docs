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



contentTypes, err := graphClient.Sites().BySiteId("site-id").Lists().ByListId("list-id").ContentTypes().Get(context.Background(), nil)


```