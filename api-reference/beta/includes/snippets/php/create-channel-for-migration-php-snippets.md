---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Channel();
$requestBody->setDisplayName('Import_150958_99z');
$requestBody->setDescription('Import_150958_99z');
$requestBody->setCreatedDateTime(new \DateTime('2020-03-14T11:22:17.067Z'));
$additionalData = [
	'@microsoft.graph.channelCreationMode' => 'migration',
];
$requestBody->setAdditionalData($additionalData);

$result = $graphServiceClient->teams()->byTeamId('team-id')->channels()->post($requestBody)->wait();

```