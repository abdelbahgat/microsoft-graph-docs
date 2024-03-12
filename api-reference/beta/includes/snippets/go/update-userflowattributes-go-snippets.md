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


requestBody := graphmodels.NewIdentityUserFlowAttribute()
description := "Your new hobby"
requestBody.SetDescription(&description) 

result, err := graphClient.Identity().UserFlowAttributes().ByUserFlowAttributeId("identityUserFlowAttribute-id").Patch(context.Background(), requestBody, nil)


```