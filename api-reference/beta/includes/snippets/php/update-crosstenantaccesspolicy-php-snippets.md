---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CrossTenantAccessPolicy();
$requestBody->setAllowedCloudEndpoints(['microsoftonline.us', 'partner.microsoftonline.cn', 	]);

$result = $graphServiceClient->policies()->crossTenantAccessPolicy()->patch($requestBody)->wait();

```