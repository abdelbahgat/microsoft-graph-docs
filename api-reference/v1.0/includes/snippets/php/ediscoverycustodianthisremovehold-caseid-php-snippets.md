---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new RemoveHoldPostRequestBody();
$requestBody->setIds(['39333641443238353535383731453339', '46333131344239353834433430454335', 	]);

$graphServiceClient->security()->cases()->ediscoveryCases()->byEdiscoveryCaseId('ediscoveryCase-id')->noncustodialDataSources()->microsoftGraphSecurityRemoveHold()->post($requestBody)->wait();

```