---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewSectionGroup()
displayName := "Section group name"
requestBody.SetDisplayName(&displayName) 

result, err := graphClient.Me().Onenote().Notebooks().ByNotebookId("notebook-id").SectionGroups().Post(context.Background(), requestBody, nil)


```