---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new BusinessScenario();
$requestBody->setOdataType('#microsoft.graph.businessScenario');
$requestBody->setDisplayName('Contoso Order Tracking');
$requestBody->setUniqueName('com.contoso.apps.ordertracking');

$result = $graphServiceClient->solutions()->businessScenarios()->post($requestBody)->wait();

```