---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewExtension()
additionalData := map[string]interface{}{
	"extensionName" : "Com.Contoso.Estimate", 
	"companyName" : "Contoso", 
	"expirationDate" : "2016-07-30T11:00:00.000Z", 
	"dealValue" : int32(1010100) , 
	topPicks := []string {
		"Employees only",
		"Add spouse or guest",
		"Add family",
	}
}
requestBody.SetAdditionalData(additionalData)

extensions, err := graphClient.Groups().ByGroupId("group-id").Threads().ByConversationThreadId("conversationThread-id").Posts().ByPostId("post-id").Extensions().ByExtensionId("extension-id").Patch(context.Background(), requestBody, nil)


```