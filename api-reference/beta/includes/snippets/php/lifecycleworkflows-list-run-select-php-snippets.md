---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new RunsRequestBuilderGetRequestConfiguration();
$queryParameters = RunsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->select = ["id","failedTasksCount","failedUsersCount","processingStatus","totalTasksCount","totalUnprocessedTasksCount","totalUsersCount","id"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->identityGovernance()->lifecycleWorkflows()->workflows()->byWorkflowId('workflow-id')->runs()->get($requestConfiguration)->wait();

```