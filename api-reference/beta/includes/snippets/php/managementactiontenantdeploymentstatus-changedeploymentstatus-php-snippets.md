---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ChangeDeploymentStatusPostRequestBody();
$requestBody->setTenantGroupId('String');
$requestBody->setTenantId('String');
$requestBody->setManagementActionId('String');
$requestBody->setManagementTemplateId('String');
$requestBody->setStatus('String');

$result = $graphServiceClient->tenantRelationships()->managedTenants()->managementActionTenantDeploymentStatuses()->microsoftGraphManagedTenantsChangeDeploymentStatus()->post($requestBody)->wait();

```