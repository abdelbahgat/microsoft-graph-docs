---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new IosManagedAppProtection();
$requestBody->setOdataType('#microsoft.graph.iosManagedAppProtection');
$requestBody->setDisplayName('Display Name value');
$requestBody->setDescription('Description value');
$requestBody->setVersion('Version value');
$requestBody->setPeriodOfflineBeforeAccessCheck(new \DateInterval('-PT17.1357909S'));
$requestBody->setPeriodOnlineBeforeAccessCheck(new \DateInterval('PT35.0018757S'));
$requestBody->setAllowedInboundDataTransferSources(new ManagedAppDataTransferLevel('managedApps'));
$requestBody->setAllowedOutboundDataTransferDestinations(new ManagedAppDataTransferLevel('managedApps'));
$requestBody->setOrganizationalCredentialsRequired(true);
$requestBody->setAllowedOutboundClipboardSharingLevel(new ManagedAppClipboardSharingLevel('managedAppsWithPasteIn'));
$requestBody->setDataBackupBlocked(true);
$requestBody->setDeviceComplianceRequired(true);
$requestBody->setManagedBrowserToOpenLinksRequired(true);
$requestBody->setSaveAsBlocked(true);
$requestBody->setPeriodOfflineBeforeWipeIsEnforced(new \DateInterval('-PT3M22.1587532S'));
$requestBody->setPinRequired(true);
$requestBody->setMaximumPinRetries(1);
$requestBody->setSimplePinBlocked(true);
$requestBody->setMinimumPinLength(0);
$requestBody->setPinCharacterSet(new ManagedAppPinCharacterSet('alphanumericAndSymbol'));
$requestBody->setPeriodBeforePinReset(new \DateInterval('PT3M29.6631862S'));
$requestBody->setAllowedDataStorageLocations([new ManagedAppDataStorageLocation('sharePoint'),	]);
$requestBody->setContactSyncBlocked(true);
$requestBody->setPrintBlocked(true);
$requestBody->setFingerprintBlocked(true);
$requestBody->setDisableAppPinIfDevicePinIsSet(true);
$requestBody->setMinimumRequiredOsVersion('Minimum Required Os Version value');
$requestBody->setMinimumWarningOsVersion('Minimum Warning Os Version value');
$requestBody->setMinimumRequiredAppVersion('Minimum Required App Version value');
$requestBody->setMinimumWarningAppVersion('Minimum Warning App Version value');
$requestBody->setManagedBrowser(new ManagedBrowserType('microsoftEdge'));
$requestBody->setIsAssigned(true);
$requestBody->setAppDataEncryptionType(new ManagedAppDataEncryptionType('afterDeviceRestart'));
$requestBody->setMinimumRequiredSdkVersion('Minimum Required Sdk Version value');
$requestBody->setDeployedAppCount(0);
$requestBody->setFaceIdBlocked(true);
$requestBody->setCustomBrowserProtocol('Custom Browser Protocol value');

$result = $graphServiceClient->deviceAppManagement()->iosManagedAppProtections()->byIosManagedAppProtectionId('iosManagedAppProtection-id')->patch($requestBody)->wait();

```