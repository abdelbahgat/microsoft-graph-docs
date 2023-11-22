---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Channel();
$requestBody->setDisplayName('UpdateChannelModeration');
$requestBody->setDescription('Update channel moderation.');
$moderationSettings = new ChannelModerationSettings();
$moderationSettings->setUserNewMessageRestriction(new UserNewMessageRestriction('moderators'));
$moderationSettings->setReplyRestriction(new ReplyRestriction('everyone'));
$moderationSettings->setAllowNewMessageFromBots(true);
$moderationSettings->setAllowNewMessageFromConnectors(true);
$requestBody->setModerationSettings($moderationSettings);

$result = $graphServiceClient->teams()->byTeamId('team-id')->channels()->byChannelId('channel-id')->patch($requestBody)->wait();

```