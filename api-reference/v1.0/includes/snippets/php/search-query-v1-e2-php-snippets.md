---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new QueryPostRequestBody();
$requestsSearchRequest1 = new SearchRequest();
$requestsSearchRequest1->setEntityTypes([new EntityType('listItem'),	]);
$requestsSearchRequest1Query = new SearchQuery();
$requestsSearchRequest1Query->setQueryString('contoso');
$requestsSearchRequest1Query->setQueryTemplate('{searchTerms} CreatedBy:Bob');
$requestsSearchRequest1->setQuery($requestsSearchRequest1Query);
$requestsSearchRequest1->setFrom(0);
$requestsSearchRequest1->setSize(25);
$requestsArray []= $requestsSearchRequest1;
$requestBody->setRequests($requestsArray);


$result = $graphServiceClient->search()->query()->post($requestBody)->wait();

```