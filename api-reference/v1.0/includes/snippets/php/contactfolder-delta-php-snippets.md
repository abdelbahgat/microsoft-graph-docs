---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new DeltaRequestBuilderGetRequestConfiguration();

$headers = [
	'Prefer' => 'odata.maxpagesize=2',
];

$requestConfiguration->headers = $headers;


$requestResult = $graphServiceClient->me()->contactFolders()->delta()->get($requestConfiguration);


```