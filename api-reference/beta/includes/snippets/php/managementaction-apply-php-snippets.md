---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new ApplyPostRequestBody();
$requestBody->setTenantId('String');

$requestBody->setTenantGroupId('String');

$requestBody->setManagementTemplateId('String');



$requestResult = $graphServiceClient->tenantRelationships()->managedTenants()->managementActionsById('managementAction-id')->apply()->post($requestBody);


```