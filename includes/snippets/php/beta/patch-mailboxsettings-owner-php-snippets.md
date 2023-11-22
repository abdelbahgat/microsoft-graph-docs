---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new MailboxSettings();
$requestBody->setDelegateMeetingMessageDeliveryOptions(new DelegateMeetingMessageDeliveryOptions('sendToDelegateAndPrincipal'));

$result = $graphServiceClient->users()->byUserId('user-id')->mailboxSettings()->patch($requestBody)->wait();

```