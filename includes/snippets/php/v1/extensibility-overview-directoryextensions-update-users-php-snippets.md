---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new User();
$additionalData = [
	'extension_b7d8e648520f41d3b9c0fdeb91768a0a_permanent_pensionable' => null,
	'extension_b7d8e648520f41d3b9c0fdeb91768a0a_jobGroupTracker' => 'E4',
];
$requestBody->setAdditionalData($additionalData);

$result = $graphServiceClient->users()->byUserId('user-id')->patch($requestBody)->wait();

```