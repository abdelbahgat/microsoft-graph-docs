---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new RetentionEventType();
$requestBody->setOdataType('#microsoft.graph.security.retentionEventType');
$requestBody->setDisplayName('String');
$requestBody->setDescription('String');
$createdBy = new IdentitySet();
$createdBy->setOdataType('microsoft.graph.identitySet');
$requestBody->setCreatedBy($createdBy);

$result = $graphServiceClient->security()->triggerTypes()->retentionEventTypes()->post($requestBody)->wait();

```