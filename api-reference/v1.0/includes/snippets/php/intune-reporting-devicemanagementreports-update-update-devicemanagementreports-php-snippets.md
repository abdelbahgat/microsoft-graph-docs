---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new DeviceManagementReports();
$requestBody->setOdataType('#microsoft.graph.deviceManagementReports');

$result = $graphServiceClient->deviceManagement()->reports()->patch($requestBody)->wait();

```