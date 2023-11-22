---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new DeviceComplianceSettingState();
$requestBody->setOdataType('#microsoft.graph.deviceComplianceSettingState');
$requestBody->setSetting('Setting value');
$requestBody->setSettingName('Setting Name value');
$requestBody->setDeviceId('Device Id value');
$requestBody->setDeviceName('Device Name value');
$requestBody->setUserId('User Id value');
$requestBody->setUserEmail('User Email value');
$requestBody->setUserName('User Name value');
$requestBody->setUserPrincipalName('User Principal Name value');
$requestBody->setDeviceModel('Device Model value');
$requestBody->setState(new ComplianceStatus('notApplicable'));
$requestBody->setComplianceGracePeriodExpirationDateTime(new \DateTime('2016-12-31T23:56:44.951111-08:00'));

$result = $graphServiceClient->deviceManagement()->deviceCompliancePolicySettingStateSummaries()->byDeviceCompliancePolicySettingStateSummaryId('deviceCompliancePolicySettingStateSummary-id')->deviceComplianceSettingStates()->post($requestBody)->wait();

```