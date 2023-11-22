---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Simulation();
$requestBody->setId('2f5548d1-0dd8-4cc8-9de0-e0d6ec7ea3dc');
$requestBody->setStatus(new SimulationStatus('cancelled'));
$additionalData = [
	'@odata.etag' => '\"0100aa9b-0000-0100-0000-6396fa270000\"',
];
$requestBody->setAdditionalData($additionalData);

$result = $graphServiceClient->security()->attackSimulation()->simulations()->bySimulationId('simulation-id')->patch($requestBody)->wait();

```