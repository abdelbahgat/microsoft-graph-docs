---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new TenantSearchPostRequestBody();
$requestBody->setTenantId('String');

$result = $graphServiceClient->tenantRelationships()->managedTenants()->tenantGroups()->microsoftGraphManagedTenantsTenantSearch()->post($requestBody)->wait();

```