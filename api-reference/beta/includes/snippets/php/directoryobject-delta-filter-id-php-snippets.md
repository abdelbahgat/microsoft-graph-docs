---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new DeltaRequestBuilderGetRequestConfiguration();
$queryParameters = DeltaRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->filter = "id eq '87d349ed-44d7-43e1-9a83-5f2406dee5bd'";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->directoryObjects()->delta()->get($requestConfiguration)->wait();

```