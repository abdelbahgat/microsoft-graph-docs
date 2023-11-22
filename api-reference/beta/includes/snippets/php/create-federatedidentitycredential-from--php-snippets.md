---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new FederatedIdentityCredential();
$requestBody->setName('testing02');
$requestBody->setIssuer('https://login.microsoftonline.com/3d1e2be9-a10a-4a0c-8380-7ce190f98ed9/v2.0');
$requestBody->setSubject('a7d388c3-5e3f-4959-ac7d-786b3383006a');
$requestBody->setAudiences(['api://AzureADTokenExchange', 	]);

$result = $graphServiceClient->applications()->byApplicationId('application-id')->federatedIdentityCredentials()->post($requestBody)->wait();

```