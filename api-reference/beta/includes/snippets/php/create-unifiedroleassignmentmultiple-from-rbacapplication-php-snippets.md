---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new UnifiedRoleAssignmentMultiple();
$requestBody->setOdataType('#microsoft.graph.unifiedRoleAssignmentMultiple');
$requestBody->setDisplayName('My test role assignment 1');
$requestBody->setRoleDefinitionId('c2cf284d-6c41-4e6b-afac-4b80928c9034');
$requestBody->setPrincipalIds(['f8ca5a85-489a-49a0-b555-0a6d81e56f0d', 'c1518aa9-4da5-4c84-a902-a31404023890', 	]);
$requestBody->setDirectoryScopeIds(['28ca5a85-489a-49a0-b555-0a6d81e56f0d', '8152656a-cf9a-4928-a457-1512d4cae295', 	]);

$result = $graphServiceClient->roleManagement()->deviceManagement()->roleAssignments()->post($requestBody)->wait();

```