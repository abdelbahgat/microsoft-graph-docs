---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new EmailAuthenticationMethod();
$requestBody->setEmailAddress('kim@contoso.com');

$result = $graphServiceClient->users()->byUserId('user-id')->authentication()->emailMethods()->post($requestBody)->wait();

```