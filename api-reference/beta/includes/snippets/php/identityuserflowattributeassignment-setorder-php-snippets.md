---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new SetOrderPostRequestBody();
$newAssignmentOrder = new AssignmentOrder();
$newAssignmentOrder->setOrder(['City', 'extension_GUID_ShoeSize', 	]);
$requestBody->setNewAssignmentOrder($newAssignmentOrder);

$graphServiceClient->identity()->b2cUserFlows()->byB2cIdentityUserFlowId('b2cIdentityUserFlow-id')->userAttributeAssignments()->setOrder()->post($requestBody)->wait();

```