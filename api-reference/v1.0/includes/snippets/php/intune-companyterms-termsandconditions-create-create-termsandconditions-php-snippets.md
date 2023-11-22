---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new TermsAndConditions();
$requestBody->setOdataType('#microsoft.graph.termsAndConditions');
$requestBody->setDisplayName('Display Name value');
$requestBody->setDescription('Description value');
$requestBody->setTitle('Title value');
$requestBody->setBodyText('Body Text value');
$requestBody->setAcceptanceStatement('Acceptance Statement value');
$requestBody->setVersion(7);

$result = $graphServiceClient->deviceManagement()->termsAndConditions()->post($requestBody)->wait();

```