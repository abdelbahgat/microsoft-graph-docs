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


requestBody := graphmodels.NewMessageRule()
displayName := "Important from partner"
requestBody.SetDisplayName(&displayName) 
actions := graphmodels.NewMessageRuleActions()
markImportance := graphmodels.HIGH_IMPORTANCE 
actions.SetMarkImportance(&markImportance) 
requestBody.SetActions(actions)

messageRules, err := graphClient.Me().MailFolders().ByMailFolderId("mailFolder-id").MessageRules().ByMessageRuleId("messageRule-id").Patch(context.Background(), requestBody, nil)


```