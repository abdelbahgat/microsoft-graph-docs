---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ScheduledPermissionsRequest();
$requestedPermissions = new AwsPermissionsDefinition();
$requestedPermissions->setOdataType('#microsoft.graph.awsPermissionsDefinition');
$requestedPermissionsAuthorizationSystemInfo = new PermissionsDefinitionAuthorizationSystem();
$requestedPermissionsAuthorizationSystemInfo->setAuthorizationSystemId('956987887735');
$requestedPermissionsAuthorizationSystemInfo->setAuthorizationSystemType('AWS');
$requestedPermissions->setAuthorizationSystemInfo($requestedPermissionsAuthorizationSystemInfo);
$requestedPermissionsActionInfo = new AwsPolicyPermissionsDefinitionAction();
$requestedPermissionsActionInfo->setOdataType('microsoft.graph.awsPolicyPermissionsDefinitionAction');
$policiesPermissionsDefinitionAwsPolicy1 = new PermissionsDefinitionAwsPolicy();
$policiesPermissionsDefinitionAwsPolicy1->setId('arn:aws:iam::956987887735:policy/AddUserToGroup');
$policiesArray []= $policiesPermissionsDefinitionAwsPolicy1;
$requestedPermissionsActionInfo->setPolicies($policiesArray);

$requestedPermissionsActionInfo->setAssignToRoleId('arn:aws:aim::956987887735:role/saml-user');
$requestedPermissions->setActionInfo($requestedPermissionsActionInfo);
$requestedPermissionsIdentityInfo = new PermissionsDefinitionAuthorizationSystemIdentity();
$requestedPermissionsIdentityInfo->setExternalId('alex@contoso.com');
$requestedPermissionsIdentityInfoSource = new SamlIdentitySource();
$requestedPermissionsIdentityInfoSource->setOdataType('microsoft.graph.samlIdentitySource');
$requestedPermissionsIdentityInfo->setSource($requestedPermissionsIdentityInfoSource);
$requestedPermissionsIdentityInfo->setIdentityType(new PermissionsDefinitionIdentityType('user'));
$requestedPermissions->setIdentityInfo($requestedPermissionsIdentityInfo);
$requestBody->setRequestedPermissions($requestedPermissions);
$requestBody->setJustification('I need to do this because I want to add a user to a group');
$requestBody->setNotes('Pretty Please');
$scheduleInfo = new RequestSchedule();
$scheduleInfoExpiration = new ExpirationPattern();
$scheduleInfoExpiration->setDuration(new \DateInterval('PT1H'));
$scheduleInfo->setExpiration($scheduleInfoExpiration);
$requestBody->setScheduleInfo($scheduleInfo);
$ticketInfo = new TicketInfo();
$ticketInfo->setTicketNumber('INC1234567');
$ticketInfo->setTicketSystem('ServiceNow');
$ticketInfo->setTicketSubmitterIdentityId('alex@contoso.com');
$ticketInfo->setTicketApproverIdentityId('alexmanager@contoso.com');
$requestBody->setTicketInfo($ticketInfo);

$result = $graphServiceClient->identityGovernance()->permissionsManagement()->scheduledPermissionsRequests()->post($requestBody)->wait();

```