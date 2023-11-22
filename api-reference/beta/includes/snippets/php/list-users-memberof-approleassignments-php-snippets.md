---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new GraphGroupRequestBuilderGetRequestConfiguration();
$queryParameters = GraphGroupRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->filter = "appRoleAssignments/\$count gt 0";
$queryParameters->select = ["id","displayName"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->users()->byUserId('user-id')->memberOf()->graphGroup()->get($requestConfiguration)->wait();

```