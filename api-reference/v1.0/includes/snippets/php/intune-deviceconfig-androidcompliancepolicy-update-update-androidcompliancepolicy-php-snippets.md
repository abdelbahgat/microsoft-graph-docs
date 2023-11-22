---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AndroidCompliancePolicy();
$requestBody->setOdataType('#microsoft.graph.androidCompliancePolicy');
$requestBody->setDescription('Description value');
$requestBody->setDisplayName('Display Name value');
$requestBody->setVersion(7);
$requestBody->setPasswordRequired(true);
$requestBody->setPasswordMinimumLength(5);
$requestBody->setPasswordRequiredType(new AndroidRequiredPasswordType('alphabetic'));
$requestBody->setPasswordMinutesOfInactivityBeforeLock(5);
$requestBody->setPasswordExpirationDays(6);
$requestBody->setPasswordPreviousPasswordBlockCount(2);
$requestBody->setSecurityPreventInstallAppsFromUnknownSources(true);
$requestBody->setSecurityDisableUsbDebugging(true);
$requestBody->setSecurityRequireVerifyApps(true);
$requestBody->setDeviceThreatProtectionEnabled(true);
$requestBody->setDeviceThreatProtectionRequiredSecurityLevel(new DeviceThreatProtectionLevel('secured'));
$requestBody->setSecurityBlockJailbrokenDevices(true);
$requestBody->setOsMinimumVersion('Os Minimum Version value');
$requestBody->setOsMaximumVersion('Os Maximum Version value');
$requestBody->setMinAndroidSecurityPatchLevel('Min Android Security Patch Level value');
$requestBody->setStorageRequireEncryption(true);
$requestBody->setSecurityRequireSafetyNetAttestationBasicIntegrity(true);
$requestBody->setSecurityRequireSafetyNetAttestationCertifiedDevice(true);
$requestBody->setSecurityRequireGooglePlayServices(true);
$requestBody->setSecurityRequireUpToDateSecurityProviders(true);
$requestBody->setSecurityRequireCompanyPortalAppIntegrity(true);

$result = $graphServiceClient->deviceManagement()->deviceCompliancePolicies()->byDeviceCompliancePolicyId('deviceCompliancePolicy-id')->patch($requestBody)->wait();

```