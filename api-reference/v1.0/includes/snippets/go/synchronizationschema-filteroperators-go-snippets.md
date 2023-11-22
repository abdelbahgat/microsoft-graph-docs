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



filterOperators, err := graphClient.ServicePrincipals().ByServicePrincipalId("servicePrincipal-id").Synchronization().Jobs().BySynchronizationJobId("synchronizationJob-id").Schema().FilterOperators().Get(context.Background(), nil)


```