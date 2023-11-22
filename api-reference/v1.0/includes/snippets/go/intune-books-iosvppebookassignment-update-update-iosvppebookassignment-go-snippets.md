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


requestBody := graphmodels.NewManagedEBookAssignment()
target := graphmodels.NewDeviceAndAppManagementAssignmentTarget()
requestBody.SetTarget(target)
installIntent := graphmodels.REQUIRED_INSTALLINTENT 
requestBody.SetInstallIntent(&installIntent) 

assignments, err := graphClient.DeviceAppManagement().ManagedEBooks().ByManagedEBookId("managedEBook-id").Assignments().ByManagedEBookAssignmentId("managedEBookAssignment-id").Patch(context.Background(), requestBody, nil)


```