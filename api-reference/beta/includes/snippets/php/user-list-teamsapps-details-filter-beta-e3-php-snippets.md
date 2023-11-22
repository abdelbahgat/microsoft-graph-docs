---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new InstalledAppsRequestBuilderGetRequestConfiguration();
$queryParameters = InstalledAppsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->expand = ["teamsApp","teamsAppDefinition"];
$queryParameters->filter = "teamsApp/externalId eq 'cf1ba4c7-f94e-4d80-ba90-5594b641a8ee'";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->users()->byUserId('user-id')->teamwork()->installedApps()->get($requestConfiguration)->wait();

```