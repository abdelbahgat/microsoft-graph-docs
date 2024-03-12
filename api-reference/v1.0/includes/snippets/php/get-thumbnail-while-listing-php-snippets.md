---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new ChildrenRequestBuilderGetRequestConfiguration();
$queryParameters = ChildrenRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->expand = ["thumbnails"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->drivesById('drive-id')->itemsById('driveItem-id')->children()->get($requestConfiguration);


```