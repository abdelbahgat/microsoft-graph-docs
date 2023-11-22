---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new ServicePrincipalsRequestBuilderGetRequestConfiguration();
$queryParameters = ServicePrincipalsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->filter = "appId eq '00000002-0000-0000-c000-000000000000'";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->servicePrincipals()->get($requestConfiguration)->wait();

```