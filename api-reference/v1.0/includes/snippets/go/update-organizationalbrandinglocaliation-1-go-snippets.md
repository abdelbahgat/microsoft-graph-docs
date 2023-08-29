---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"Accept-Language": "0",
}
configuration := &graphconfig.BrandingRequestBuilderPatchRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewOrganizationalBranding()
signInPageText := "Default"
requestBody.SetSignInPageText(&signInPageText) 
usernameHintText := "DefaultHint"
requestBody.SetUsernameHintText(&usernameHintText) 

graphClient.OrganizationById("organization-id").Branding().PatchWithRequestConfigurationAndResponseHandler(requestBody, configuration, nil)


```