---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new TeamworkTag();
$requestBody->setDisplayName('Finance');
$membersTeamworkTagMember1 = new TeamworkTagMember();
$membersTeamworkTagMember1->setUserId('92f6952f-61ca-4a94-8910-508a240bc167');
$membersArray []= $membersTeamworkTagMember1;
$membersTeamworkTagMember2 = new TeamworkTagMember();
$membersTeamworkTagMember2->setUserId('085d800c-b86b-4bfc-a857-9371ad1caf29');
$membersArray []= $membersTeamworkTagMember2;
$requestBody->setMembers($membersArray);


$result = $graphServiceClient->teams()->byTeamId('team-id')->tags()->post($requestBody)->wait();

```