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


requestBody := graphusers.NewItemCopyPostRequestBody()
destinationId := "destinationId-value"
requestBody.SetDestinationId(&destinationId) 

copy, err := graphClient.Me().MailFolders().ByMailFolderId("mailFolder-id").Copy().Post(context.Background(), requestBody, nil)


```