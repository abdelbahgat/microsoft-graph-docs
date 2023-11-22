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


requestBody := graphmodels.NewCloudPcProvisioningPolicy()
displayName := "HR provisioning policy"
requestBody.SetDisplayName(&displayName) 
description := "Provisioning policy for India HR employees"
requestBody.SetDescription(&description) 
onPremisesConnectionId := "4e47d0f6-6f77-44f0-8893-c0fe1701ffff"
requestBody.SetOnPremisesConnectionId(&onPremisesConnectionId) 
imageId := "Image ID value"
requestBody.SetImageId(&imageId) 
imageDisplayName := "Image Display Name value"
requestBody.SetImageDisplayName(&imageDisplayName) 
imageType := graphmodels.CUSTOM_CLOUDPCPROVISIONINGPOLICYIMAGETYPE 
requestBody.SetImageType(&imageType) 
windowsSettings := graphmodels.NewCloudPcWindowsSettings()
language := "en-US"
windowsSettings.SetLanguage(&language) 
requestBody.SetWindowsSettings(windowsSettings)

provisioningPolicies, err := graphClient.DeviceManagement().VirtualEndpoint().ProvisioningPolicies().ByCloudPcProvisioningPolicyId("cloudPcProvisioningPolicy-id").Patch(context.Background(), requestBody, nil)


```