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


requestBody := graphmodels.NewAccessPackageAssignmentRequest()
requestType := "AdminRemove"
requestBody.SetRequestType(&requestType) 
accessPackageAssignment := graphmodels.NewAccessPackageAssignment()
id := "a6bb6942-3ae1-4259-9908-0133aaee9377"
accessPackageAssignment.SetId(&id) 
requestBody.SetAccessPackageAssignment(accessPackageAssignment)

accessPackageAssignmentRequests, err := graphClient.IdentityGovernance().EntitlementManagement().AccessPackageAssignmentRequests().Post(context.Background(), requestBody, nil)


```