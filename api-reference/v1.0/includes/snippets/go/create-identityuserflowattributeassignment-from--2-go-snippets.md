---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewIdentityUserFlowAttributeAssignment()
isOptional := false
requestBody.SetIsOptional(&isOptional) 
requiresVerification := false
requestBody.SetRequiresVerification(&requiresVerification) 
userInputType := graphmodels.TEXTBOX_IDENTITYUSERFLOWATTRIBUTEINPUTTYPE 
requestBody.SetUserInputType(&userInputType) 
displayName := "Shoe size"
requestBody.SetDisplayName(&displayName) 
userAttributeValues := []graphmodels.UserAttributeValuesItemable {

}
requestBody.SetUserAttributeValues(userAttributeValues)
userAttribute := graphmodels.NewIdentityUserFlowAttribute()
id := "extension_guid_shoeSize"
userAttribute.SetId(&id) 
requestBody.SetUserAttribute(userAttribute)

result, err := graphClient.Identity().B2xUserFlows().ByB2xUserFlowId("b2xIdentityUserFlow-id").UserAttributeAssignments().Post(context.Background(), requestBody, nil)


```