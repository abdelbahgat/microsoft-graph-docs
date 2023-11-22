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


requestBody := graphmodels.NewPermissionGrantConditionSet()
permissionType := graphmodels.DELEGATED_PERMISSIONTYPE 
requestBody.SetPermissionType(&permissionType) 
certifiedClientApplicationsOnly := true
requestBody.SetCertifiedClientApplicationsOnly(&certifiedClientApplicationsOnly) 

includes, err := graphClient.Policies().PermissionGrantPolicies().ByPermissionGrantPolicyId("permissionGrantPolicy-id").Includes().Post(context.Background(), requestBody, nil)


```