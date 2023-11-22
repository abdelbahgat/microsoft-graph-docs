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



claimsMappingPolicies, err := graphClient.ServicePrincipals().ByServicePrincipalId("servicePrincipal-id").ClaimsMappingPolicies().Get(context.Background(), nil)


```