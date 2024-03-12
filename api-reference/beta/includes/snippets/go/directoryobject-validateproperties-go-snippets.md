---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  "github.com/google/uuid"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/DirectoryObjects/ValidateProperties"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewValidatePropertiesPostRequestBody()
entityType := "Group"
requestBody.SetEntityType(&entityType) 
displayName := "Myprefix_test_mysuffix"
requestBody.SetDisplayName(&displayName) 
mailNickname := "Myprefix_test_mysuffix"
requestBody.SetMailNickname(&mailNickname) 
onBehalfOfUserId := uuid.MustParse("onBehalfOfUserId-value")
requestBody.SetOnBehalfOfUserId(&onBehalfOfUserId) 

graphClient.DirectoryObjects().ValidateProperties().Post(context.Background(), requestBody, nil)


```