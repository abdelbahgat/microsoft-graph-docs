---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new TeamsRequestBuilderGetRequestConfiguration();

$queryParameters = new TeamsRequestBuilderGetQueryParameters();
$queryParameters->filter = "displayName eq 'A Contoso Team'";
$queryParameters->select = ["id","description"];

$requestConfiguration->queryParameters = $queryParameters;


$requestResult = $graphServiceClient->teams()->get($requestConfiguration);


```