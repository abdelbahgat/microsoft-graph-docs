---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new IdentityProvider();
$additionalData = [
	'responseType' => 'id_token',
];
$requestBody->setAdditionalData($additionalData);

$result = $graphServiceClient->identityProviders()->byIdentityProviderId('identityProvider-id')->patch($requestBody)->wait();

```