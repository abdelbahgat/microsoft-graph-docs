---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphusers "github.com/microsoftgraph/msgraph-sdk-go/users"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphusers.NewItemCopyNotebookPostRequestBody()
groupId := "groupId-value"
requestBody.SetGroupId(&groupId) 
renameAs := "renameAs-value"
requestBody.SetRenameAs(&renameAs) 

copyNotebook, err := graphClient.Me().Onenote().Notebooks().ByNotebookId("notebook-id").CopyNotebook().Post(context.Background(), requestBody, nil)


```