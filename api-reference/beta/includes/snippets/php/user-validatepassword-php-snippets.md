---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ValidatePasswordPostRequestBody();
$requestBody->setPassword('1234567890');

$result = $graphServiceClient->users()->validatePassword()->post($requestBody)->wait();

```