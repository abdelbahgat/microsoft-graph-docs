---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ExternalConnection();
$requestBody->setId('contosohr');
$requestBody->setName('Contoso HR');
$requestBody->setDescription('Connection to index Contoso HR system');

$result = $graphServiceClient->external()->connections()->post($requestBody)->wait();

```