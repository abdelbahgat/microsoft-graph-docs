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


requestBody := graphmodels.NewOrganization()
mobileDeviceManagementAuthority := graphmodels.INTUNE_MDMAUTHORITY 
requestBody.SetMobileDeviceManagementAuthority(&mobileDeviceManagementAuthority) 

organization, err := graphClient.Organization().ByOrganizationId("organization-id").Patch(context.Background(), requestBody, nil)


```