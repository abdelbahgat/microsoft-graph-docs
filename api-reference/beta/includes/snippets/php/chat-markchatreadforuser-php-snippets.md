---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new MarkChatReadForUserPostRequestBody();
$user = new TeamworkUserIdentity();
$user->setId('d864e79f-a516-4d0f-9fee-0eeb4d61fdc2');
$additionalData = [
	'tenantId' => '2a690434-97d9-4eed-83a6-f5f13600199a',
];
$user->setAdditionalData($additionalData);
$requestBody->setUser($user);

$graphServiceClient->chats()->byChatId('chat-id')->markChatReadForUser()->post($requestBody)->wait();

```