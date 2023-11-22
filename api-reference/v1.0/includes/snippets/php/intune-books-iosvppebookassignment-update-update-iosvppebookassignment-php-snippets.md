---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new IosVppEBookAssignment();
$requestBody->setOdataType('#microsoft.graph.iosVppEBookAssignment');
$target = new DeviceAndAppManagementAssignmentTarget();
$target->setOdataType('microsoft.graph.deviceAndAppManagementAssignmentTarget');
$requestBody->setTarget($target);
$requestBody->setInstallIntent(new InstallIntent('required'));

$result = $graphServiceClient->deviceAppManagement()->managedEBooks()->byManagedEBookId('managedEBook-id')->assignments()->byManagedEBookAssignmentId('managedEBookAssignment-id')->patch($requestBody)->wait();

```