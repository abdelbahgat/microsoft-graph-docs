---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



appRoleAssignedTo, err := graphClient.ServicePrincipals().ByServicePrincipalId("servicePrincipal-id").AppRoleAssignedTo().Get(context.Background(), nil)


```