---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ContactMergeSuggestions();
$requestBody->setIsEnabled(false);

$result = $graphServiceClient->me()->settings()->contactMergeSuggestions()->patch($requestBody)->wait();

```