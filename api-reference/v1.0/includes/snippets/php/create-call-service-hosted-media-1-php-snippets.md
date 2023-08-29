---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new Call();
$requestBody->set@odatatype('#microsoft.graph.call');

$requestBody->setCallbackUri('https://bot.contoso.com/callback');

$targetsInvitationParticipantInfo1 = new InvitationParticipantInfo();
$targetsInvitationParticipantInfo1->set@odatatype('#microsoft.graph.invitationParticipantInfo');

$targetsInvitationParticipantInfo1Identity = new IdentitySet();
$targetsInvitationParticipantInfo1Identity->set@odatatype('#microsoft.graph.identitySet');

$targetsInvitationParticipantInfo1IdentityUser = new Identity();
$targetsInvitationParticipantInfo1IdentityUser->set@odatatype('#microsoft.graph.identity');

$targetsInvitationParticipantInfo1IdentityUser->setDisplayName('John');

$targetsInvitationParticipantInfo1IdentityUser->setId('112f7296-5fa4-42ca-bae8-6a692b15d4b8');


$targetsInvitationParticipantInfo1Identity->setUser($targetsInvitationParticipantInfo1IdentityUser);

$targetsInvitationParticipantInfo1->setIdentity($targetsInvitationParticipantInfo1Identity);

$targetsArray []= $targetsInvitationParticipantInfo1;
$requestBody->setTargets($targetsArray);


$requestBody->setRequestedModalities(['audio', ]);

$mediaConfig = new MediaConfig();
$mediaConfig->set@odatatype('#microsoft.graph.serviceHostedMediaConfig');


$requestBody->setMediaConfig($mediaConfig);


$requestResult = $graphServiceClient->communications()->calls()->post($requestBody);


```