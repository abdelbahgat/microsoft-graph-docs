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



internalSponsors, err := graphClient.IdentityGovernance().EntitlementManagement().ConnectedOrganizations().ByConnectedOrganizationId("connectedOrganization-id").InternalSponsors().Get(context.Background(), nil)


```