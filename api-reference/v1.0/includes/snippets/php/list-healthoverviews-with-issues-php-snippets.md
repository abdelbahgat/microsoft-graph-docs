---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new HealthOverviewsRequestBuilderGetRequestConfiguration();
$queryParameters = HealthOverviewsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->expand = ["issues"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->admin()->serviceAnnouncement()->healthOverviews()->get($requestConfiguration)->wait();

```