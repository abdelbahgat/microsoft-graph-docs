---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Channel();
$requestBody->setDisplayName('Architecture Discussion');
$requestBody->setDescription('This channel is where we debate all future architecture plans');
$requestBody->setMembershipType(new ChannelMembershipType('standard'));

$result = $graphServiceClient->teams()->byTeamId('team-id')->channels()->post($requestBody)->wait();

```