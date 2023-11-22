---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewManagedDeviceMobileAppConfiguration()
targetedMobileApps := []string {
	"Targeted Mobile Apps value",
}
requestBody.SetTargetedMobileApps(targetedMobileApps)
description := "Description value"
requestBody.SetDescription(&description) 
displayName := "Display Name value"
requestBody.SetDisplayName(&displayName) 
version := int32(7)
requestBody.SetVersion(&version) 
encodedSettingXml := []byte("zW5jb2RlZFNldHRpbmdYbWw=")
requestBody.SetEncodedSettingXml(&encodedSettingXml) 


appConfigurationSettingItem := graphmodels.NewAppConfigurationSettingItem()
appConfigKey := "App Config Key value"
appConfigurationSettingItem.SetAppConfigKey(&appConfigKey) 
appConfigKeyType := graphmodels.INTEGERTYPE_MDMAPPCONFIGKEYTYPE 
appConfigurationSettingItem.SetAppConfigKeyType(&appConfigKeyType) 
appConfigKeyValue := "App Config Key Value value"
appConfigurationSettingItem.SetAppConfigKeyValue(&appConfigKeyValue) 

settings := []graphmodels.AppConfigurationSettingItemable {
	appConfigurationSettingItem,
}
requestBody.SetSettings(settings)

mobileAppConfigurations, err := graphClient.DeviceAppManagement().MobileAppConfigurations().ByManagedDeviceMobileAppConfigurationId("managedDeviceMobileAppConfiguration-id").Patch(context.Background(), requestBody, nil)


```