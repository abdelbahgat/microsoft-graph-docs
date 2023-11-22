---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new GetByIdsPostRequestBody();
$requestBody->setIds(['84b80893-8749-40a3-97b7-68513b600544', '5d6059b6-368d-45f8-91e1-8e07d485f1d0', '0b944de3-e0fc-4774-a49a-b135213725ef', 'b75a5ab2-fe55-4463-bd31-d21ad555c6e0', 	]);
$requestBody->setTypes(['user', 'group', 'device', 	]);

$result = $graphServiceClient->directoryObjects()->getByIds()->post($requestBody)->wait();

```