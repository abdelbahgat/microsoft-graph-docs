---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new EvaluateDynamicMembershipPostRequestBody();
$requestBody->setMemberId('319b41e8-d9e4-42f8-bdc9-741113f48b33');

$result = $graphServiceClient->groups()->byGroupId('group-id')->evaluateDynamicMembership()->post($requestBody)->wait();

```