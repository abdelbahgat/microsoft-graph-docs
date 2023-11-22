---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CloudPcUserSetting();
$requestBody->setOdataType('#microsoft.graph.cloudPcUserSetting');
$requestBody->setDisplayName('Example');
$requestBody->setSelfServiceEnabled(false);
$requestBody->setLocalAdminEnabled(true);
$restorePointSetting = new CloudPcRestorePointSetting();
$restorePointSetting->setFrequencyInHours(16);
$restorePointSetting->setUserRestoreEnabled(true);
$requestBody->setRestorePointSetting($restorePointSetting);

$result = $graphServiceClient->deviceManagement()->virtualEndpoint()->userSettings()->post($requestBody)->wait();

```