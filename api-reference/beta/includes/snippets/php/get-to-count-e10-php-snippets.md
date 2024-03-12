---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new UsersRequestBuilderGetRequestConfiguration();
$headers = [
		'ConsistencyLevel' => 'eventual',
	];
$requestConfiguration->headers = $headers;

$queryParameters = UsersRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->search = "\"displayName:wa\" OR \"displayName:ad\"";
$queryParameters->orderby = ["displayName"];
$queryParameters->count = true;
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->users()->get($requestConfiguration);


```