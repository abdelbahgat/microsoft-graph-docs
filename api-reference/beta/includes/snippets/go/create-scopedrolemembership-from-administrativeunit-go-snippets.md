---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewScopedRoleMembership()
roleId := "roleId-value"
requestBody.SetRoleId(&roleId) 
roleMemberInfo := graphmodels.NewIdentity()
id := "id-value"
roleMemberInfo.SetId(&id) 
requestBody.SetRoleMemberInfo(roleMemberInfo)

result, err := graphClient.AdministrativeUnitsById("administrativeUnit-id").ScopedRoleMembers().Post(requestBody)


```