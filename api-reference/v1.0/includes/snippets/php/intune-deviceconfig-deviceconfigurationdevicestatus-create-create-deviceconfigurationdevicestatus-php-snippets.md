---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new DeviceConfigurationDeviceStatus();
$requestBody->setOdataType('#microsoft.graph.deviceConfigurationDeviceStatus');
$requestBody->setDeviceDisplayName('Device Display Name value');
$requestBody->setUserName('User Name value');
$requestBody->setDeviceModel('Device Model value');
$requestBody->setComplianceGracePeriodExpirationDateTime(new \DateTime('2016-12-31T23:56:44.951111-08:00'));
$requestBody->setStatus(new ComplianceStatus('notApplicable'));
$requestBody->setLastReportedDateTime(new \DateTime('2017-01-01T00:00:17.7769392-08:00'));
$requestBody->setUserPrincipalName('User Principal Name value');

$result = $graphServiceClient->deviceManagement()->deviceConfigurations()->byDeviceConfigurationId('deviceConfiguration-id')->deviceStatuses()->post($requestBody)->wait();

```