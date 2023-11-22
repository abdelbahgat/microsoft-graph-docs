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


requestBody := graphmodels.NewDeviceCompliancePolicy()
description := "Description value"
requestBody.SetDescription(&description) 
displayName := "Display Name value"
requestBody.SetDisplayName(&displayName) 
version := int32(7)
requestBody.SetVersion(&version) 
passwordBlockSimple := true
requestBody.SetPasswordBlockSimple(&passwordBlockSimple) 
passwordExpirationDays := int32(6)
requestBody.SetPasswordExpirationDays(&passwordExpirationDays) 
passwordMinimumLength := int32(5)
requestBody.SetPasswordMinimumLength(&passwordMinimumLength) 
passwordMinutesOfInactivityBeforeLock := int32(5)
requestBody.SetPasswordMinutesOfInactivityBeforeLock(&passwordMinutesOfInactivityBeforeLock) 
passwordMinimumCharacterSetCount := int32(0)
requestBody.SetPasswordMinimumCharacterSetCount(&passwordMinimumCharacterSetCount) 
passwordRequiredType := graphmodels.ALPHANUMERIC_REQUIREDPASSWORDTYPE 
requestBody.SetPasswordRequiredType(&passwordRequiredType) 
passwordPreviousPasswordBlockCount := int32(2)
requestBody.SetPasswordPreviousPasswordBlockCount(&passwordPreviousPasswordBlockCount) 
passwordRequired := true
requestBody.SetPasswordRequired(&passwordRequired) 
osMinimumVersion := "Os Minimum Version value"
requestBody.SetOsMinimumVersion(&osMinimumVersion) 
osMaximumVersion := "Os Maximum Version value"
requestBody.SetOsMaximumVersion(&osMaximumVersion) 
storageRequireEncryption := true
requestBody.SetStorageRequireEncryption(&storageRequireEncryption) 

deviceCompliancePolicies, err := graphClient.DeviceManagement().DeviceCompliancePolicies().Post(context.Background(), requestBody, nil)


```