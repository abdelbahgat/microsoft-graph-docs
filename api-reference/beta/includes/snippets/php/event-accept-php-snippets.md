---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AcceptPostRequestBody();
$requestBody->setComment('comment-value');
$requestBody->setSendResponse(true);

$graphServiceClient->me()->events()->byEventId('event-id')->accept()->post($requestBody)->wait();

```