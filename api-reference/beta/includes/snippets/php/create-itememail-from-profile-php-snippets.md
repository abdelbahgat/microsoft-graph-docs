---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ItemEmail();
$requestBody->setAddress('Innocenty.Popov@adventureworks.com');

$result = $graphServiceClient->me()->profile()->emails()->post($requestBody)->wait();

```