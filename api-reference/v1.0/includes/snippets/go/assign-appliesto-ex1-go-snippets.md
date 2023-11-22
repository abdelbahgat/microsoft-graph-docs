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


requestBody := graphmodels.NewReferenceCreate()
odataId := "https://graph.microsoft.com/v1.0/policies/appManagementPolicies/{id}"
requestBody.SetOdataId(&odataId) 

graphClient.Applications().ByApplicationId("application-id").AppManagementPolicies().Ref().Post(context.Background(), requestBody, nil)


```