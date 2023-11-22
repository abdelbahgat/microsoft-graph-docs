---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new User();
$onPremisesExtensionAttributes = new OnPremisesExtensionAttributes();
$onPremisesExtensionAttributes->setExtensionAttribute1('skypeId.adeleVance');
$onPremisesExtensionAttributes->setExtensionAttribute13(null);
$requestBody->setOnPremisesExtensionAttributes($onPremisesExtensionAttributes);

$result = $graphServiceClient->users()->byUserId('user-id')->patch($requestBody)->wait();

```