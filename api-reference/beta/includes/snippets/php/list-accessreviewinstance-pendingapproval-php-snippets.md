---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new PendingAccessReviewInstancesRequestBuilderGetRequestConfiguration();
$queryParameters = PendingAccessReviewInstancesRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->expand = ["definition"];
$queryParameters->top = 100;
$queryParameters->skip = 0;
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->me()->pendingAccessReviewInstances()->get($requestConfiguration)->wait();

```