---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new TaskDefinitionsRequestBuilderGetRequestConfiguration();
$queryParameters = TaskDefinitionsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->filter = "category has 'joiner'";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->identityGovernance()->lifecycleWorkflows()->taskDefinitions()->get($requestConfiguration)->wait();

```