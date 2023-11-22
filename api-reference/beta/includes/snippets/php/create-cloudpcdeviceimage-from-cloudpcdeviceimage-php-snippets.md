---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CloudPcDeviceImage();
$requestBody->setOdataType('#microsoft.graph.cloudPcDeviceImage');
$requestBody->setDisplayName('Display Name value');
$requestBody->setOsBuildNumber('OS Build Number value');
$requestBody->setOperatingSystem('Operating System value');
$requestBody->setVersion('Version value');
$requestBody->setSourceImageResourceId('/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c58ffff/resourceGroups/Example/providers/Microsoft.Compute/images/exampleImage');

$result = $graphServiceClient->deviceManagement()->virtualEndpoint()->deviceImages()->post($requestBody)->wait();

```