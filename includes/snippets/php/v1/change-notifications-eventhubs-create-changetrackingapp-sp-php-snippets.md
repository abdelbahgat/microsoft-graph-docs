---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ServicePrincipal();
$requestBody->setAppId('0bf30f3b-4a52-48df-9a82-234910c4a086');

$result = $graphServiceClient->servicePrincipals()->post($requestBody)->wait();

```