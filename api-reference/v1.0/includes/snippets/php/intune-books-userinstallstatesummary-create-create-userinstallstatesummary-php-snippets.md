---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new UserInstallStateSummary();
$requestBody->setOdataType('#microsoft.graph.userInstallStateSummary');
$requestBody->setUserName('User Name value');
$requestBody->setInstalledDeviceCount(4);
$requestBody->setFailedDeviceCount(1);
$requestBody->setNotInstalledDeviceCount(7);

$result = $graphServiceClient->deviceAppManagement()->managedEBooks()->byManagedEBookId('managedEBook-id')->userStateSummary()->post($requestBody)->wait();

```