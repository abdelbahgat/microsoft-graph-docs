---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new IdentityUserFlowAttribute();
$requestBody->setDisplayName('Hobby');
$requestBody->setDescription('Your hobby');
$requestBody->setDataType(new IdentityUserFlowAttributeDataType('string'));

$result = $graphServiceClient->identity()->userFlowAttributes()->post($requestBody)->wait();

```