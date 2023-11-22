---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new WindowsPhone81GeneralConfiguration();
$requestBody->setOdataType('#microsoft.graph.windowsPhone81GeneralConfiguration');
$requestBody->setDescription('Description value');
$requestBody->setDisplayName('Display Name value');
$requestBody->setVersion(7);
$requestBody->setApplyOnlyToWindowsPhone81(true);
$requestBody->setAppsBlockCopyPaste(true);
$requestBody->setBluetoothBlocked(true);
$requestBody->setCameraBlocked(true);
$requestBody->setCellularBlockWifiTethering(true);
$compliantAppsListAppListItem1 = new AppListItem();
$compliantAppsListAppListItem1->setOdataType('microsoft.graph.appListItem');
$compliantAppsListAppListItem1->setName('Name value');
$compliantAppsListAppListItem1->setPublisher('Publisher value');
$compliantAppsListAppListItem1->setAppStoreUrl('https://example.com/appStoreUrl/');
$compliantAppsListAppListItem1->setAppId('App Id value');
$compliantAppsListArray []= $compliantAppsListAppListItem1;
$requestBody->setCompliantAppsList($compliantAppsListArray);

$requestBody->setCompliantAppListType(new AppListType('appsInListCompliant'));
$requestBody->setDiagnosticDataBlockSubmission(true);
$requestBody->setEmailBlockAddingAccounts(true);
$requestBody->setLocationServicesBlocked(true);
$requestBody->setMicrosoftAccountBlocked(true);
$requestBody->setNfcBlocked(true);
$requestBody->setPasswordBlockSimple(true);
$requestBody->setPasswordExpirationDays(6);
$requestBody->setPasswordMinimumLength(5);
$requestBody->setPasswordMinutesOfInactivityBeforeScreenTimeout(14);
$requestBody->setPasswordMinimumCharacterSetCount(0);
$requestBody->setPasswordPreviousPasswordBlockCount(2);
$requestBody->setPasswordSignInFailureCountBeforeFactoryReset(12);
$requestBody->setPasswordRequiredType(new RequiredPasswordType('alphanumeric'));
$requestBody->setPasswordRequired(true);
$requestBody->setScreenCaptureBlocked(true);
$requestBody->setStorageBlockRemovableStorage(true);
$requestBody->setStorageRequireEncryption(true);
$requestBody->setWebBrowserBlocked(true);
$requestBody->setWifiBlocked(true);
$requestBody->setWifiBlockAutomaticConnectHotspots(true);
$requestBody->setWifiBlockHotspotReporting(true);
$requestBody->setWindowsStoreBlocked(true);

$result = $graphServiceClient->deviceManagement()->deviceConfigurations()->byDeviceConfigurationId('deviceConfiguration-id')->patch($requestBody)->wait();

```