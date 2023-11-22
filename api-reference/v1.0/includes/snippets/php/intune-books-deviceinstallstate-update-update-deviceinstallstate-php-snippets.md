---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new DeviceInstallState();
$requestBody->setOdataType('#microsoft.graph.deviceInstallState');
$requestBody->setDeviceName('Device Name value');
$requestBody->setDeviceId('Device Id value');
$requestBody->setLastSyncDateTime(new \DateTime('2017-01-01T00:02:49.3205976-08:00'));
$requestBody->setInstallState(new InstallState('installed'));
$requestBody->setErrorCode('Error Code value');
$requestBody->setOsVersion('Os Version value');
$requestBody->setOsDescription('Os Description value');
$requestBody->setUserName('User Name value');

$result = $graphServiceClient->deviceAppManagement()->managedEBooks()->byManagedEBookId('managedEBook-id')->deviceStates()->byDeviceInstallStateId('deviceInstallState-id')->patch($requestBody)->wait();

```