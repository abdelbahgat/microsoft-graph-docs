---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new ApplicationsRequestBuilderGetRequestConfiguration();
$headers = [
		'ConsistencyLevel' => 'eventual',
	];
$requestConfiguration->headers = $headers;

$queryParameters = ApplicationsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->search = "\"displayName:Web\"";
$queryParameters->count = true;
$queryParameters->select = ["appId","identifierUris","displayName","publisherDomain","signInAudience"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->applications()->get($requestConfiguration)->wait();

```