---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new PersonName();
$requestBody->setNickname('Kesha');

$result = $graphServiceClient->me()->profile()->names()->byPersonNameId('personName-id')->patch($requestBody)->wait();

```