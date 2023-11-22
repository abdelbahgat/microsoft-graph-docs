---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new ExportJobsRequestBuilderGetRequestConfiguration();
$queryParameters = ExportJobsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->filter = " explorerViewId eq ‘9ab0fcab-c1d4-4b26-963b-a3c33155f853’";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->employeeExperience()->goals()->exportJobs()->get($requestConfiguration)->wait();

```