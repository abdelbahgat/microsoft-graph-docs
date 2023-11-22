---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new DeviceComplianceUserStatus();
$requestBody->setOdataType('#microsoft.graph.deviceComplianceUserStatus');
$requestBody->setUserDisplayName('User Display Name value');
$requestBody->setDevicesCount(12);
$requestBody->setStatus(new ComplianceStatus('notApplicable'));
$requestBody->setLastReportedDateTime(new \DateTime('2017-01-01T00:00:17.7769392-08:00'));
$requestBody->setUserPrincipalName('User Principal Name value');

$result = $graphServiceClient->deviceManagement()->deviceCompliancePolicies()->byDeviceCompliancePolicyId('deviceCompliancePolicy-id')->userStatuses()->byDeviceComplianceUserStatusId('deviceComplianceUserStatus-id')->patch($requestBody)->wait();

```