---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ReportRoot();
$requestBody->setOdataType('#microsoft.graph.reportRoot');

$result = $graphServiceClient->reports()->patch($requestBody)->wait();

```