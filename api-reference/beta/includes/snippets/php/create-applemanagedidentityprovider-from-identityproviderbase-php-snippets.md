---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AppleManagedIdentityProvider();
$requestBody->setOdataType('microsoft.graph.appleManagedIdentityProvider');
$requestBody->setDisplayName('Sign in with Apple');
$requestBody->setDeveloperId('UBF8T346G9');
$requestBody->setServiceId('com.microsoft.rts.b2c.test.client');
$requestBody->setKeyId('99P6D879C4');
$requestBody->setCertificateData('******');

$result = $graphServiceClient->identity()->identityProviders()->post($requestBody)->wait();

```