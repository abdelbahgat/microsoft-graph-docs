---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AndroidWorkProfileGeneralDeviceConfiguration();
$requestBody->setOdataType('#microsoft.graph.androidWorkProfileGeneralDeviceConfiguration');
$requestBody->setDescription('Description value');
$requestBody->setDisplayName('Display Name value');
$requestBody->setVersion(7);
$requestBody->setPasswordBlockFingerprintUnlock(true);
$requestBody->setPasswordBlockTrustAgents(true);
$requestBody->setPasswordExpirationDays(6);
$requestBody->setPasswordMinimumLength(5);
$requestBody->setPasswordMinutesOfInactivityBeforeScreenTimeout(14);
$requestBody->setPasswordPreviousPasswordBlockCount(2);
$requestBody->setPasswordSignInFailureCountBeforeFactoryReset(12);
$requestBody->setPasswordRequiredType(new AndroidWorkProfileRequiredPasswordType('lowSecurityBiometric'));
$requestBody->setWorkProfileDataSharingType(new AndroidWorkProfileCrossProfileDataSharingType('preventAny'));
$requestBody->setWorkProfileBlockNotificationsWhileDeviceLocked(true);
$requestBody->setWorkProfileBlockAddingAccounts(true);
$requestBody->setWorkProfileBluetoothEnableContactSharing(true);
$requestBody->setWorkProfileBlockScreenCapture(true);
$requestBody->setWorkProfileBlockCrossProfileCallerId(true);
$requestBody->setWorkProfileBlockCamera(true);
$requestBody->setWorkProfileBlockCrossProfileContactsSearch(true);
$requestBody->setWorkProfileBlockCrossProfileCopyPaste(true);
$requestBody->setWorkProfileDefaultAppPermissionPolicy(new AndroidWorkProfileDefaultAppPermissionPolicyType('prompt'));
$requestBody->setWorkProfilePasswordBlockFingerprintUnlock(true);
$requestBody->setWorkProfilePasswordBlockTrustAgents(true);
$requestBody->setWorkProfilePasswordExpirationDays(1);
$requestBody->setWorkProfilePasswordMinimumLength(0);
$requestBody->setWorkProfilePasswordMinNumericCharacters(7);
$requestBody->setWorkProfilePasswordMinNonLetterCharacters(9);
$requestBody->setWorkProfilePasswordMinLetterCharacters(6);
$requestBody->setWorkProfilePasswordMinLowerCaseCharacters(9);
$requestBody->setWorkProfilePasswordMinUpperCaseCharacters(9);
$requestBody->setWorkProfilePasswordMinSymbolCharacters(6);
$requestBody->setWorkProfilePasswordMinutesOfInactivityBeforeScreenTimeout(9);
$requestBody->setWorkProfilePasswordPreviousPasswordBlockCount(13);
$requestBody->setWorkProfilePasswordSignInFailureCountBeforeFactoryReset(7);
$requestBody->setWorkProfilePasswordRequiredType(new AndroidWorkProfileRequiredPasswordType('lowSecurityBiometric'));
$requestBody->setWorkProfileRequirePassword(true);
$requestBody->setSecurityRequireVerifyApps(true);

$result = $graphServiceClient->deviceManagement()->deviceConfigurations()->byDeviceConfigurationId('deviceConfiguration-id')->patch($requestBody)->wait();

```