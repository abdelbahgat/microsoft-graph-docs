---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new LegalHold();
$requestBody->setDescription('This is a description for a legalHold');

$result = $graphServiceClient->compliance()->ediscovery()->cases()->byCaseId('case-id')->legalHolds()->byLegalHoldId('legalHold-id')->patch($requestBody)->wait();

```