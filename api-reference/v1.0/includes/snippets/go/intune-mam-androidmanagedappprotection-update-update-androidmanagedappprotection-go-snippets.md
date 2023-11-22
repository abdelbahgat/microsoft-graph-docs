---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  abstractions "github.com/microsoft/kiota-abstractions-go"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewAndroidManagedAppProtection()
displayName := "Display Name value"
requestBody.SetDisplayName(&displayName) 
description := "Description value"
requestBody.SetDescription(&description) 
version := "Version value"
requestBody.SetVersion(&version) 
periodOfflineBeforeAccessCheck , err := abstractions.ParseISODuration("-PT17.1357909S")
requestBody.SetPeriodOfflineBeforeAccessCheck(&periodOfflineBeforeAccessCheck) 
periodOnlineBeforeAccessCheck , err := abstractions.ParseISODuration("PT35.0018757S")
requestBody.SetPeriodOnlineBeforeAccessCheck(&periodOnlineBeforeAccessCheck) 
allowedInboundDataTransferSources := graphmodels.MANAGEDAPPS_MANAGEDAPPDATATRANSFERLEVEL 
requestBody.SetAllowedInboundDataTransferSources(&allowedInboundDataTransferSources) 
allowedOutboundDataTransferDestinations := graphmodels.MANAGEDAPPS_MANAGEDAPPDATATRANSFERLEVEL 
requestBody.SetAllowedOutboundDataTransferDestinations(&allowedOutboundDataTransferDestinations) 
organizationalCredentialsRequired := true
requestBody.SetOrganizationalCredentialsRequired(&organizationalCredentialsRequired) 
allowedOutboundClipboardSharingLevel := graphmodels.MANAGEDAPPSWITHPASTEIN_MANAGEDAPPCLIPBOARDSHARINGLEVEL 
requestBody.SetAllowedOutboundClipboardSharingLevel(&allowedOutboundClipboardSharingLevel) 
dataBackupBlocked := true
requestBody.SetDataBackupBlocked(&dataBackupBlocked) 
deviceComplianceRequired := true
requestBody.SetDeviceComplianceRequired(&deviceComplianceRequired) 
managedBrowserToOpenLinksRequired := true
requestBody.SetManagedBrowserToOpenLinksRequired(&managedBrowserToOpenLinksRequired) 
saveAsBlocked := true
requestBody.SetSaveAsBlocked(&saveAsBlocked) 
periodOfflineBeforeWipeIsEnforced , err := abstractions.ParseISODuration("-PT3M22.1587532S")
requestBody.SetPeriodOfflineBeforeWipeIsEnforced(&periodOfflineBeforeWipeIsEnforced) 
pinRequired := true
requestBody.SetPinRequired(&pinRequired) 
maximumPinRetries := int32(1)
requestBody.SetMaximumPinRetries(&maximumPinRetries) 
simplePinBlocked := true
requestBody.SetSimplePinBlocked(&simplePinBlocked) 
minimumPinLength := int32(0)
requestBody.SetMinimumPinLength(&minimumPinLength) 
pinCharacterSet := graphmodels.ALPHANUMERICANDSYMBOL_MANAGEDAPPPINCHARACTERSET 
requestBody.SetPinCharacterSet(&pinCharacterSet) 
periodBeforePinReset , err := abstractions.ParseISODuration("PT3M29.6631862S")
requestBody.SetPeriodBeforePinReset(&periodBeforePinReset) 
allowedDataStorageLocations := []graphmodels.ManagedAppDataStorageLocationable {
	managedAppDataStorageLocation := graphmodels.SHAREPOINT_MANAGEDAPPDATASTORAGELOCATION 
	requestBody.SetManagedAppDataStorageLocation(&managedAppDataStorageLocation)
}
requestBody.SetAllowedDataStorageLocations(allowedDataStorageLocations)
contactSyncBlocked := true
requestBody.SetContactSyncBlocked(&contactSyncBlocked) 
printBlocked := true
requestBody.SetPrintBlocked(&printBlocked) 
fingerprintBlocked := true
requestBody.SetFingerprintBlocked(&fingerprintBlocked) 
disableAppPinIfDevicePinIsSet := true
requestBody.SetDisableAppPinIfDevicePinIsSet(&disableAppPinIfDevicePinIsSet) 
minimumRequiredOsVersion := "Minimum Required Os Version value"
requestBody.SetMinimumRequiredOsVersion(&minimumRequiredOsVersion) 
minimumWarningOsVersion := "Minimum Warning Os Version value"
requestBody.SetMinimumWarningOsVersion(&minimumWarningOsVersion) 
minimumRequiredAppVersion := "Minimum Required App Version value"
requestBody.SetMinimumRequiredAppVersion(&minimumRequiredAppVersion) 
minimumWarningAppVersion := "Minimum Warning App Version value"
requestBody.SetMinimumWarningAppVersion(&minimumWarningAppVersion) 
managedBrowser := graphmodels.MICROSOFTEDGE_MANAGEDBROWSERTYPE 
requestBody.SetManagedBrowser(&managedBrowser) 
isAssigned := true
requestBody.SetIsAssigned(&isAssigned) 
screenCaptureBlocked := true
requestBody.SetScreenCaptureBlocked(&screenCaptureBlocked) 
disableAppEncryptionIfDeviceEncryptionIsEnabled := true
requestBody.SetDisableAppEncryptionIfDeviceEncryptionIsEnabled(&disableAppEncryptionIfDeviceEncryptionIsEnabled) 
encryptAppData := true
requestBody.SetEncryptAppData(&encryptAppData) 
deployedAppCount := int32(0)
requestBody.SetDeployedAppCount(&deployedAppCount) 
minimumRequiredPatchVersion := "Minimum Required Patch Version value"
requestBody.SetMinimumRequiredPatchVersion(&minimumRequiredPatchVersion) 
minimumWarningPatchVersion := "Minimum Warning Patch Version value"
requestBody.SetMinimumWarningPatchVersion(&minimumWarningPatchVersion) 
customBrowserPackageId := "Custom Browser Package Id value"
requestBody.SetCustomBrowserPackageId(&customBrowserPackageId) 
customBrowserDisplayName := "Custom Browser Display Name value"
requestBody.SetCustomBrowserDisplayName(&customBrowserDisplayName) 

androidManagedAppProtections, err := graphClient.DeviceAppManagement().AndroidManagedAppProtections().ByAndroidManagedAppProtectionId("androidManagedAppProtection-id").Patch(context.Background(), requestBody, nil)


```