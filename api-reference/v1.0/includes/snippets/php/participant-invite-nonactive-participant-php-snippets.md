---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new InvitePostRequestBody();
$participantsInvitationParticipantInfo1 = new InvitationParticipantInfo();
$participantsInvitationParticipantInfo1->setOdataType('#microsoft.graph.invitationParticipantInfo');
$participantsInvitationParticipantInfo1Identity = new IdentitySet();
$participantsInvitationParticipantInfo1Identity->setOdataType('#microsoft.graph.identitySet');
$participantsInvitationParticipantInfo1IdentityUser = new Identity();
$participantsInvitationParticipantInfo1IdentityUser->setOdataType('#microsoft.graph.identity');
$participantsInvitationParticipantInfo1IdentityUser->setId('278405a3-f568-4b3e-b684-009193463064');
$additionalData = [
	'identityProvider' => 'AAD',
];
$participantsInvitationParticipantInfo1IdentityUser->setAdditionalData($additionalData);
$participantsInvitationParticipantInfo1Identity->setUser($participantsInvitationParticipantInfo1IdentityUser);
$participantsInvitationParticipantInfo1->setIdentity($participantsInvitationParticipantInfo1Identity);
$participantsInvitationParticipantInfo1->setParticipantId('a7ebfb2d-871e-419c-87af-27290b22e8db');
$participantsArray []= $participantsInvitationParticipantInfo1;
$requestBody->setParticipants($participantsArray);

$requestBody->setClientContext('f2fa86af-3c51-4bc2-8fc0-475452d9764f');

$result = $graphServiceClient->communications()->calls()->byCallId('call-id')->participants()->invite()->post($requestBody)->wait();

```