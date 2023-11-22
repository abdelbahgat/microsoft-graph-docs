---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewMailFolder()
displayName := "displayName-value"
requestBody.SetDisplayName(&displayName) 
isHidden := true
requestBody.SetIsHidden(&isHidden) 

childFolders, err := graphClient.Me().MailFolders().ByMailFolderId("mailFolder-id").ChildFolders().Post(context.Background(), requestBody, nil)


```