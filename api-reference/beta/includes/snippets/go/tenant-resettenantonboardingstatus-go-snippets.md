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



microsoftGraphManagedTenantsResetTenantOnboardingStatus, err := graphClient.TenantRelationships().ManagedTenants().Tenants().ByTenantId("tenant-id").MicrosoftGraphManagedTenantsResetTenantOnboardingStatus().Post(context.Background(), nil)


```