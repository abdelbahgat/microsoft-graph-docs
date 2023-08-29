---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new RiskyUsersRequestBuilderGetRequestConfiguration();

$queryParameters = new RiskyUsersRequestBuilderGetQueryParameters();
$queryParameters->filter = "riskLevel eq microsoft.graph.riskLevel'medium'";

$requestConfiguration->queryParameters = $queryParameters;


$requestResult = $graphServiceClient->identityProtection()->riskyUsers()->get($requestConfiguration);


```