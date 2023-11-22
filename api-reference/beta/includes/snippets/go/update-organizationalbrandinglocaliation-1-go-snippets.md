---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  abstractions "github.com/microsoft/kiota-abstractions-go"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  graphorganization "github.com/microsoftgraph/msgraph-beta-sdk-go/organization"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


headers := abstractions.NewRequestHeaders()
headers.Add("Accept-Language", "0")

configuration := &graphorganization.OrganizationItemBrandingRequestBuilderPatchRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewOrganizationalBranding()
signInPageText := "Default"
requestBody.SetSignInPageText(&signInPageText) 
usernameHintText := "DefaultHint"
requestBody.SetUsernameHintText(&usernameHintText) 

branding, err := graphClient.Organization().ByOrganizationId("organization-id").Branding().Patch(context.Background(), requestBody, configuration)


```