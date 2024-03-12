---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new MessagesRequestBuilderGetRequestConfiguration();
$queryParameters = MessagesRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->top = 2;
$queryParameters->orderby = ["lastModifiedDateTime desc"];
$queryParameters->filter = "lastModifiedDateTime gt 2022-09-22T00:00:00.000Z and lastModifiedDateTime lt 2022-09-24T00:00:00.000Z";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->chatsById('chat-id')->messages()->get($requestConfiguration);


```