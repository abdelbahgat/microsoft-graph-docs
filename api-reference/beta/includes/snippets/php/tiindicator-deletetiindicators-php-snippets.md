---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new DeleteTiIndicatorsPostRequestBody();
$requestBody->setValue(['id-value1', 'id-value2', 	]);

$result = $graphServiceClient->security()->tiIndicators()->deleteTiIndicators()->post($requestBody)->wait();

```