---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new WorkforceIntegration();
$requestBody->setDisplayName('displayName-value');
$requestBody->setApiVersion(99);
$encryption = new WorkforceIntegrationEncryption();
$encryption->setProtocol(new WorkforceIntegrationEncryptionProtocol('protocol-value'));
$encryption->setSecret('secret-value');
$requestBody->setEncryption($encryption);
$requestBody->setIsActive(true);
$requestBody->setUrl('url-value');
$requestBody->setSupports(new WorkforceIntegrationSupportedEntities('supports-value'));

$result = $graphServiceClient->teamwork()->workforceIntegrations()->post($requestBody)->wait();

```