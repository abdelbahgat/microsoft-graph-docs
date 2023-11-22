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


requestBody := graphmodels.NewUnifiedRoleManagementAlertConfiguration()
isEnabled := true
requestBody.SetIsEnabled(&isEnabled) 
globalAdminCountThreshold := int32(4)
requestBody.SetGlobalAdminCountThreshold(&globalAdminCountThreshold) 
percentageOfGlobalAdminsOutOfRolesThreshold := int32(10)
requestBody.SetPercentageOfGlobalAdminsOutOfRolesThreshold(&percentageOfGlobalAdminsOutOfRolesThreshold) 

alertConfigurations, err := graphClient.IdentityGovernance().RoleManagementAlerts().AlertConfigurations().ByUnifiedRoleManagementAlertConfigurationId("unifiedRoleManagementAlertConfiguration-id").Patch(context.Background(), requestBody, nil)


```