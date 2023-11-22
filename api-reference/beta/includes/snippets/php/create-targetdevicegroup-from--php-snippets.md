---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new TargetDeviceGroup();
$requestBody->setOdataType('#microsoft.graph.targetDeviceGroup');
$requestBody->setId('b9e4eae4-b781-45a1-ce65-f2dd8ac3b696');
$requestBody->setDisplayName('Device Group A');

$result = $graphServiceClient->servicePrincipals()->byServicePrincipalId('servicePrincipal-id')->remoteDesktopSecurityConfiguration()->targetDeviceGroups()->post($requestBody)->wait();

```