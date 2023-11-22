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


requestBody := graphmodels.NewConnectedOrganization()
displayName := "Connected organization new name"
requestBody.SetDisplayName(&displayName) 
description := "Connected organization new description"
requestBody.SetDescription(&description) 
state := graphmodels.CONFIGURED_CONNECTEDORGANIZATIONSTATE 
requestBody.SetState(&state) 

connectedOrganizations, err := graphClient.IdentityGovernance().EntitlementManagement().ConnectedOrganizations().ByConnectedOrganizationId("connectedOrganization-id").Patch(context.Background(), requestBody, nil)


```