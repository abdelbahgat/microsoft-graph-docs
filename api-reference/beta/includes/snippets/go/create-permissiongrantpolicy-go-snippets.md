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


requestBody := graphmodels.NewPermissionGrantPolicy()
id := "my-custom-consent-policy"
requestBody.SetId(&id) 
displayName := "Custom application consent policy"
requestBody.SetDisplayName(&displayName) 
description := "A custom permission grant policy to customize conditions for granting consent."
requestBody.SetDescription(&description) 

permissionGrantPolicies, err := graphClient.Policies().PermissionGrantPolicies().Post(context.Background(), requestBody, nil)


```