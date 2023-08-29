---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new ListRequestBuilderGetRequestConfiguration();

$queryParameters = new ListRequestBuilderGetQueryParameters();
$queryParameters->select = ["name","lastModifiedDateTime"];
$queryParameters->expand = ["columns(select=name,description)","items",")"];

$requestConfiguration->queryParameters = $queryParameters;


$requestResult = $graphServiceClient->sitesById('site-id')->listsById('list-id')->get($requestConfiguration);


```