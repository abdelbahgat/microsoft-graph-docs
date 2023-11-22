---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new SettingStateDeviceSummary();
$requestBody->setOdataType('#microsoft.graph.settingStateDeviceSummary');
$requestBody->setSettingName('Setting Name value');
$requestBody->setInstancePath('Instance Path value');
$requestBody->setUnknownDeviceCount(2);
$requestBody->setNotApplicableDeviceCount(8);
$requestBody->setCompliantDeviceCount(4);
$requestBody->setRemediatedDeviceCount(5);
$requestBody->setNonCompliantDeviceCount(7);
$requestBody->setErrorDeviceCount(0);
$requestBody->setConflictDeviceCount(3);

$result = $graphServiceClient->deviceManagement()->deviceConfigurations()->byDeviceConfigurationId('deviceConfiguration-id')->deviceSettingStateSummaries()->bySettingStateDeviceSummaryId('settingStateDeviceSummary-id')->patch($requestBody)->wait();

```