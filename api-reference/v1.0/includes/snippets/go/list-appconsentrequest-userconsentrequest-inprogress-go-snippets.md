---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphidentitygovernance "github.com/microsoftgraph/msgraph-sdk-go/identitygovernance"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



requestFilter := "userConsentRequests/any (u:u/status eq 'InProgress')"

requestParameters := &graphidentitygovernance.IdentityGovernanceAppConsentAppConsentRequestsRequestBuilderGetQueryParameters{
	Filter: &requestFilter,
}
configuration := &graphidentitygovernance.IdentityGovernanceAppConsentAppConsentRequestsRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

appConsentRequests, err := graphClient.IdentityGovernance().AppConsent().AppConsentRequests().Get(context.Background(), configuration)


```