---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new TiIndicator();
$requestBody->setAdditionalInformation('additionalInformation-after-update');

$requestBody->setConfidence(confidence);

$requestBody->setDescription('description-after-update');


$requestConfiguration = new TiIndicatorRequestBuilderPatchRequestConfiguration();

$headers = [
	'Prefer' => 'return=representation',
];

$requestConfiguration->headers = $headers;


$graphServiceClient->security()->tiIndicatorsById('tiIndicator-id')->patch($requestBody, $requestConfiguration);


```