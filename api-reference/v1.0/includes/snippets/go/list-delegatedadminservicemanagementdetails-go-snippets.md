---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



serviceManagementDetails, err := graphClient.TenantRelationships().DelegatedAdminCustomers().ByDelegatedAdminCustomerId("delegatedAdminCustomer-id").ServiceManagementDetails().Get(context.Background(), nil)


```