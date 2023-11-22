---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new ApplicationsWithAppIdRequestBuilderGetRequestConfiguration();
$queryParameters = ApplicationsWithAppIdRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->select = ["id","appId","displayName","requiredResourceAccess"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->applicationsWithAppId('{appId}', )->get($requestConfiguration)->wait();

```