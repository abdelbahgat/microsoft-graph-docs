---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new AttributeSetsRequestBuilderGetRequestConfiguration();

$queryParameters = new AttributeSetsRequestBuilderGetQueryParameters();
$queryParameters->top = 10;

$requestConfiguration->queryParameters = $queryParameters;


$requestResult = $graphServiceClient->directory()->attributeSets()->get($requestConfiguration);


```