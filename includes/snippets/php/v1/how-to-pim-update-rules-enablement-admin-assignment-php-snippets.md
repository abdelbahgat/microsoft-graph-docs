---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new UnifiedRoleManagementPolicyEnablementRule();
$requestBody->setOdataType('#microsoft.graph.unifiedRoleManagementPolicyEnablementRule');
$requestBody->setId('Enablement_Admin_Assignment');
$requestBody->setEnabledRules(['Justification', 'MultiFactorAuthentication', 	]);
$target = new UnifiedRoleManagementPolicyRuleTarget();
$target->setOdataType('microsoft.graph.unifiedRoleManagementPolicyRuleTarget');
$target->setCaller('Admin');
$target->setOperations([new UnifiedRoleManagementPolicyRuleTargetOperations('all'),	]);
$target->setLevel('Assignment');
$target->setInheritableSettings([	]);
$target->setEnforcedSettings([	]);
$requestBody->setTarget($target);

$result = $graphServiceClient->policies()->roleManagementPolicies()->byUnifiedRoleManagementPolicyId('unifiedRoleManagementPolicy-id')->rules()->byUnifiedRoleManagementPolicyRuleId('unifiedRoleManagementPolicyRule-id')->patch($requestBody)->wait();

```