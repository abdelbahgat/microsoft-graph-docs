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



federatedIdentityCredentials, err := graphClient.Applications().ByApplicationId("application-id").FederatedIdentityCredentials().ByFederatedIdentityCredentialId("federatedIdentityCredential-id").Get(context.Background(), nil)


```