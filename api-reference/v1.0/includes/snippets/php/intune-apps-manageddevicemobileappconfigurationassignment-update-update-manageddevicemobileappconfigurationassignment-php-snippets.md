---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ManagedDeviceMobileAppConfigurationAssignment();
$requestBody->setOdataType('#microsoft.graph.managedDeviceMobileAppConfigurationAssignment');
$target = new AllLicensedUsersAssignmentTarget();
$target->setOdataType('microsoft.graph.allLicensedUsersAssignmentTarget');
$requestBody->setTarget($target);

$result = $graphServiceClient->deviceAppManagement()->mobileAppConfigurations()->byManagedDeviceMobileAppConfigurationId('managedDeviceMobileAppConfiguration-id')->assignments()->byManagedDeviceMobileAppConfigurationAssignmentId('managedDeviceMobileAppConfigurationAssignment-id')->patch($requestBody)->wait();

```