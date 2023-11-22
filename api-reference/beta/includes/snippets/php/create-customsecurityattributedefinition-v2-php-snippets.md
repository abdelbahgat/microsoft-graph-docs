---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CustomSecurityAttributeDefinition();
$requestBody->setAttributeSet('Engineering');
$requestBody->setDescription('Active projects for user');
$requestBody->setIsCollection(true);
$requestBody->setIsSearchable(true);
$requestBody->setName('Project');
$requestBody->setStatus('Available');
$requestBody->setType('String');
$requestBody->setUsePreDefinedValuesOnly(true);

$result = $graphServiceClient->directory()->customSecurityAttributeDefinitions()->post($requestBody)->wait();

```