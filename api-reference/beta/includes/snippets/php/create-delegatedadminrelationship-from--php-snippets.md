---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new DelegatedAdminRelationship();
$requestBody->setDisplayName('Contoso admin relationship');

$requestBody->setDuration('P730D');

$customer = new DelegatedAdminRelationshipCustomerParticipant();
$customer->setTenantId('4b827261-d21f-4aa9-b7db-7fa1f56fb163');

$customer->setDisplayName('Contoso subsidiary Inc');


$requestBody->setCustomer($customer);
$accessDetails = new DelegatedAdminAccessDetails();
$unifiedRolesUnifiedRole1 = new UnifiedRole();
$additionalData = [
'roleDefinitionId' => '29232cdf-9323-42fd-ade2-1d097af3e4de', 
];
$unifiedRolesUnifiedRole1->setAdditionalData($additionalData);



$unifiedRolesArray []= $unifiedRolesUnifiedRole1;
$unifiedRolesUnifiedRole2 = new UnifiedRole();
$additionalData = [
'roleDefinitionId' => '3a2c62db-5318-420d-8d74-23affee5d9d5', 
];
$unifiedRolesUnifiedRole2->setAdditionalData($additionalData);



$unifiedRolesArray []= $unifiedRolesUnifiedRole2;
$accessDetails->setUnifiedRoles($unifiedRolesArray);



$requestBody->setAccessDetails($accessDetails);


$requestResult = $graphServiceClient->tenantRelationships()->delegatedAdminRelationships()->post($requestBody);


```