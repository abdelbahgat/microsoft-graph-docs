---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new ChangeDeploymentStatusPostRequestBody();
$requestBody->setTenantGroupId('String');

$requestBody->setTenantId('String');

$requestBody->setManagementActionId('String');

$requestBody->setManagementTemplateId('String');

$requestBody->setStatus('String');



$requestResult = $graphServiceClient->tenantRelationships()->managedTenants()->managementActionTenantDeploymentStatuses()->changeDeploymentStatus()->post($requestBody);


```