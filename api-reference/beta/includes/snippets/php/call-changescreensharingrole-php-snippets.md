---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ChangeScreenSharingRolePostRequestBody();
$requestBody->setRole(new ScreenSharingRole('viewer'));

$graphServiceClient->communications()->calls()->byCallId('call-id')->changeScreenSharingRole()->post($requestBody)->wait();

```