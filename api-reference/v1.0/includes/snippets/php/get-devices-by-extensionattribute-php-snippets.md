---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new DevicesRequestBuilderGetRequestConfiguration();
$headers = [
		'ConsistencyLevel' => 'eventual',
	];
$requestConfiguration->headers = $headers;

$queryParameters = DevicesRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->filter = "extensionAttributes/extensionAttribute1 eq 'BYOD-Device'";
$queryParameters->count = true;
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->devices()->get($requestConfiguration);


```