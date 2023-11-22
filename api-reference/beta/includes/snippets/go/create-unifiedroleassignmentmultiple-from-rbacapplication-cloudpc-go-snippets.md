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


requestBody := graphmodels.NewUnifiedRoleAssignmentMultiple()
displayName := "My test role assignment 1"
requestBody.SetDisplayName(&displayName) 
description := "My role assignment description"
requestBody.SetDescription(&description) 
roleDefinitionId := "b5c08161-a7af-481c-ace2-a20a69a48fb1"
requestBody.SetRoleDefinitionId(&roleDefinitionId) 
principalIds := []string {
	"f8ca5a85-489a-49a0-b555-0a6d81e56f0d",
	"c1518aa9-4da5-4c84-a902-a31404023890",
}
requestBody.SetPrincipalIds(principalIds)

roleAssignments, err := graphClient.RoleManagement().CloudPC().RoleAssignments().Post(context.Background(), requestBody, nil)


```