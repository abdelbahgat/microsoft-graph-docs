---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewSecurityAction()
name := "BlockIp"
requestBody.SetName(&name) 
actionReason := "Test"
requestBody.SetActionReason(&actionReason) 


keyValuePair := graphmodels.NewKeyValuePair()
name := "IP"
keyValuePair.SetName(&name) 
value := "1.2.3.4"
keyValuePair.SetValue(&value) 

parameters := []graphmodels.KeyValuePairable {
	keyValuePair,
}
requestBody.SetParameters(parameters)
vendorInformation := graphmodels.NewSecurityVendorInformation()
provider := "Windows Defender ATP"
vendorInformation.SetProvider(&provider) 
vendor := "Microsoft"
vendorInformation.SetVendor(&vendor) 
requestBody.SetVendorInformation(vendorInformation)

securityActions, err := graphClient.Security().SecurityActions().Post(context.Background(), requestBody, nil)


```