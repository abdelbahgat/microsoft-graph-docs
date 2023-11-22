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


requestBody := graphmodels.NewNotebook()
displayName := "My Private notebook"
requestBody.SetDisplayName(&displayName) 

notebooks, err := graphClient.Me().Onenote().Notebooks().Post(context.Background(), requestBody, nil)


```