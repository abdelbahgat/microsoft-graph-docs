---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  abstractions "github.com/microsoft/kiota-abstractions-go"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  graphtenantrelationships "github.com/microsoftgraph/msgraph-sdk-go/tenantrelationships"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


headers := abstractions.NewRequestHeaders()
headers.Add("If-Match", "W/\"JyI0NzAwNjg0NS0wMDAwLTE5MDAtMDAwMC02MGY0Yjg4MzAwMDAiJw==\"")

configuration := &graphtenantrelationships.TenantRelationshipsDelegatedAdminRelationshipItemAccessAssignmentItemRequestBuilderPatchRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewDelegatedAdminAccessAssignment()
accessDetails := graphmodels.NewDelegatedAdminAccessDetails()


unifiedRole := graphmodels.NewUnifiedRole()
roleDefinitionId := "88d8e3e3-8f55-4a1e-953a-9b9898b8876b"
unifiedRole.SetRoleDefinitionId(&roleDefinitionId) 
unifiedRole1 := graphmodels.NewUnifiedRole()
roleDefinitionId := "44367163-eba1-44c3-98af-f5787879f96a"
unifiedRole1.SetRoleDefinitionId(&roleDefinitionId) 
unifiedRole2 := graphmodels.NewUnifiedRole()
roleDefinitionId := "729827e3-9c14-49f7-bb1b-9608f156bbb8"
unifiedRole2.SetRoleDefinitionId(&roleDefinitionId) 

unifiedRoles := []graphmodels.UnifiedRoleable {
	unifiedRole,
	unifiedRole1,
	unifiedRole2,
}
accessDetails.SetUnifiedRoles(unifiedRoles)
requestBody.SetAccessDetails(accessDetails)

accessAssignments, err := graphClient.TenantRelationships().DelegatedAdminRelationships().ByDelegatedAdminRelationshipId("delegatedAdminRelationship-id").AccessAssignments().ByDelegatedAdminAccessAssignmentId("delegatedAdminAccessAssignment-id").Patch(context.Background(), requestBody, configuration)


```