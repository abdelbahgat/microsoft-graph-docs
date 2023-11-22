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


requestBody := graphmodels.NewGroup()
description := "Contoso Life v2.0"
requestBody.SetDescription(&description) 
displayName := "Contoso Life Renewed"
requestBody.SetDisplayName(&displayName) 

groups, err := graphClient.Groups().ByGroupId("group-id").Patch(context.Background(), requestBody, nil)


```