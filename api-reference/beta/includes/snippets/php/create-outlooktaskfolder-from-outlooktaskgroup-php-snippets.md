---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new OutlookTaskFolder();
$requestBody->setName('Cooking');

$result = $graphServiceClient->me()->outlook()->taskGroups()->byOutlookTaskGroupId('outlookTaskGroup-id')->taskFolders()->post($requestBody)->wait();

```