---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CheckMemberGroupsPostRequestBody();
$requestBody->setGroupIds(['fee2c45b-915a-4a64-b130-f4eb9e75525e', '4fe90ae7-065a-478b-9400-e0a0e1cbd540', 	]);

$result = $graphServiceClient->me()->checkMemberGroups()->post($requestBody)->wait();

```