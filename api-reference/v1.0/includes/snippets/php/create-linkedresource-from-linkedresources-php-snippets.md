---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new LinkedResource();
$requestBody->setWebUrl('https://microsoft.com');
$requestBody->setApplicationName('Microsoft');
$requestBody->setDisplayName('Microsoft');
$requestBody->setExternalId('dk9cddce2-dce2-f9dd-e2dc-cdf9e2dccdf9');

$result = $graphServiceClient->me()->todo()->lists()->byTodoTaskListId('todoTaskList-id')->tasks()->byTodoTaskId('todoTask-id')->linkedResources()->post($requestBody)->wait();

```