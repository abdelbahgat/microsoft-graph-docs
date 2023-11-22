---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new UsersRequestBuilderGetRequestConfiguration();
$headers = [
		'ConsistencyLevel' => 'eventual',
	];
$requestConfiguration->headers = $headers;

$queryParameters = UsersRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->select = ["id","displayName","mail","identities"];
$queryParameters->filter = "endsWith(userPrincipalName,'";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->users()->get($requestConfiguration)->wait();

```