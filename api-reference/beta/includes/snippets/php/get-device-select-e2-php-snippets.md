---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new DeviceItemRequestBuilderGetRequestConfiguration();
$queryParameters = DeviceItemRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->select = ["id","extensionAttributes"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->devices()->byDeviceId('device-id')->get($requestConfiguration)->wait();

```