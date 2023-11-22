---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ChangeUserAccountTypePostRequestBody();
$requestBody->setUserAccountType(new CloudPcUserAccountType('administrator'));

$graphServiceClient->deviceManagement()->virtualEndpoint()->cloudPCs()->byCloudPCId('cloudPC-id')->changeUserAccountType()->post($requestBody)->wait();

```