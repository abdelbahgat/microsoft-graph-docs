---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



result, err := graphClient.Identity().ConditionalAccess().AuthenticationStrengths().Policies().ByPolicieId("authenticationStrengthPolicy-id").CombinationConfigurations().ByCombinationConfigurationId("authenticationCombinationConfiguration-id").Get(context.Background(), nil)


```