---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new UnifiedRoleAssignment();
$requestBody->setOdataType('#microsoft.graph.unifiedRoleAssignment');
$requestBody->setRoleDefinitionId('fe930be7-5e62-47db-91af-98c3a49a38b1');
$requestBody->setPrincipalId('f8ca5a85-489a-49a0-b555-0a6d81e56f0d');
$requestBody->setDirectoryScopeId('/administrativeUnits/5d107bba-d8e2-4e13-b6ae-884be90e5d1a');

$result = $graphServiceClient->roleManagement()->directory()->roleAssignments()->post($requestBody)->wait();

```