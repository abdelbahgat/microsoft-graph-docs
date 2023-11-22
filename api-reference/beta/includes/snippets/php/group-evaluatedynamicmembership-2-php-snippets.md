---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new EvaluateDynamicMembershipPostRequestBody();
$requestBody->setMemberId('319b41e8-d9e4-42f8-bdc9-741113f48b33');
$requestBody->setMembershipRule('(user.displayName -startsWith \"EndTestUser\")');

$result = $graphServiceClient->groups()->evaluateDynamicMembership()->post($requestBody)->wait();

```