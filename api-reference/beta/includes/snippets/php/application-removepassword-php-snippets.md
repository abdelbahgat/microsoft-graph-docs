---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new RemovePasswordPostRequestBody();
$requestBody->setKeyId('f0b0b335-1d71-4883-8f98-567911bfdca6');

$graphServiceClient->applications()->byApplicationId('application-id')->removePassword()->post($requestBody)->wait();

```