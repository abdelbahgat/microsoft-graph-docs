---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphadmin "github.com/microsoftgraph/msgraph-sdk-go/admin"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphadmin.NewArchivePostRequestBody()
messageIds := []string {
	"MC172851",
	"MC167983",
}
requestBody.SetMessageIds(messageIds)

archive, err := graphClient.Admin().ServiceAnnouncement().Messages().Archive().Post(context.Background(), requestBody, nil)


```