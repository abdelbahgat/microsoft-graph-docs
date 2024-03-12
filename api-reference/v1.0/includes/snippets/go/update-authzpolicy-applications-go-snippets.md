---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewAuthorizationPolicy()
defaultUserRolePermissions := graphmodels.NewDefaultUserRolePermissions()
allowedToCreateApps := false
defaultUserRolePermissions.SetAllowedToCreateApps(&allowedToCreateApps) 
requestBody.SetDefaultUserRolePermissions(defaultUserRolePermissions)

result, err := graphClient.Policies().AuthorizationPolicy().Patch(context.Background(), requestBody, nil)


```