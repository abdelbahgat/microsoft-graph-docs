---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/IdentityProtection/RiskyServicePrincipals/ConfirmCompromised"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewConfirmCompromisedPostRequestBody()
servicePrincipalIds := []string {
	"9089a539-a539-9089-39a5-899039a58990",

}
requestBody.SetServicePrincipalIds(servicePrincipalIds)

graphClient.IdentityProtection().RiskyServicePrincipals().ConfirmCompromised().Post(context.Background(), requestBody, nil)


```