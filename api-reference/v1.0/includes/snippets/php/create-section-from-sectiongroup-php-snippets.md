---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new OnenoteSection();
$requestBody->setDisplayName('Section name');

$result = $graphServiceClient->me()->onenote()->sectionGroups()->bySectionGroupId('sectionGroup-id')->sections()->post($requestBody)->wait();

```