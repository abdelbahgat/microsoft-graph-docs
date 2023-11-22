---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphusers "github.com/microsoftgraph/msgraph-beta-sdk-go/users"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestParameters := &graphusers.ItemMessageItemAttachmentItemRequestBuilderGetQueryParameters{
	Expand: [] string {"microsoft.graph.itemattachment/item"},
}
configuration := &graphusers.ItemMessageItemAttachmentItemRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

attachments, err := graphClient.Me().Messages().ByMessageId("message-id").Attachments().ByAttachmentId("attachment-id").Get(context.Background(), configuration)


```