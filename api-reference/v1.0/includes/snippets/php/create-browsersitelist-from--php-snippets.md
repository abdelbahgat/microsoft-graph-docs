---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new BrowserSiteList();
$requestBody->setDisplayName('Production Site List A');
$requestBody->setDescription('Production site list for team A');

$result = $graphServiceClient->admin()->edge()->internetExplorerMode()->siteLists()->post($requestBody)->wait();

```