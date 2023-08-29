---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new InvitePostRequestBody();
$participantsInvitationParticipantInfo1 = new InvitationParticipantInfo();
$additionalData = [
'@odata.type' => '#microsoft.graph.invitationParticipantInfo', 
'replacesCallId' => 'a7ebfb2d-871e-419c-87af-27290b22e8db', 
'identity' => $participantsInvitationParticipantInfo1 = new ();
$		participantsInvitationParticipantInfo1->set@odatatype('#microsoft.graph.identitySet');

$user = new ();
$		user->set@odatatype('#microsoft.graph.identity');

$		user->setId('7e1b4346-85a6-4bdd-abe3-d11c5d420efe');

$		user->setIdentityProvider('AAD');


$participantsInvitationParticipantInfo1->setUser($user);

$participantsInvitationParticipantInfo1->setIdentity($identity);

];
$participantsInvitationParticipantInfo1->setAdditionalData($additionalData);



$participantsArray []= $participantsInvitationParticipantInfo1;
$requestBody->setParticipants($participantsArray);


$requestBody->setClientContext('f2fa86af-3c51-4bc2-8fc0-475452d9764f');



$requestResult = $graphServiceClient->communications()->callsById('call-id')->participants()->invite()->post($requestBody);


```