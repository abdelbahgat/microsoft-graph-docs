---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new MultiTenantOrganizationMember();
$requestBody->setTenantId('4a12efe6-aa14-4d03-8dff-88fc89e2e2ad');
$requestBody->setDisplayName('Fabrikam');

$result = $graphServiceClient->tenantRelationships()->multiTenantOrganization()->tenants()->post($requestBody)->wait();

```