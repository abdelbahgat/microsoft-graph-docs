---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new MarkAsNotJunkPostRequestBody();
$requestBody->setMoveToInbox(true);

$result = $graphServiceClient->me()->messages()->byMessageId('message-id')->markAsNotJunk()->post($requestBody)->wait();

```