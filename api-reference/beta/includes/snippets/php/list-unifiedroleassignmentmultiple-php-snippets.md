---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new RoleAssignmentsRequestBuilderGetRequestConfiguration();
$queryParameters = RoleAssignmentsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->filter = "principalId eq '9e47fc6f-2d7a-464c-944e-d3dd0de522e4'";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->roleManagement()->deviceManagement()->roleAssignments()->get($requestConfiguration)->wait();

```