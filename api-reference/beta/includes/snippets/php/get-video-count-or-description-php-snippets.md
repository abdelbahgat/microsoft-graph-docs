---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new GroupsRequestBuilderGetRequestConfiguration();
$headers = [
		'ConsistencyLevel' => 'eventual',
	];
$requestConfiguration->headers = $headers;

$queryParameters = GroupsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->search = "\"displayName:Video\" OR \"description:prod\"";
$queryParameters->orderby = ["displayName"];
$queryParameters->count = true;
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->groups()->get($requestConfiguration)->wait();

```