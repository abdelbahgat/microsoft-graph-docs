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


requestBody := graphmodels.NewScopedRoleMembership()
roleId := "roleId-value"
requestBody.SetRoleId(&roleId) 
roleMemberInfo := graphmodels.NewIdentity()
id := "id-value"
roleMemberInfo.SetId(&id) 
requestBody.SetRoleMemberInfo(roleMemberInfo)

scopedRoleMembers, err := graphClient.AdministrativeUnits().ByAdministrativeUnitId("administrativeUnit-id").ScopedRoleMembers().Post(context.Background(), requestBody, nil)


```