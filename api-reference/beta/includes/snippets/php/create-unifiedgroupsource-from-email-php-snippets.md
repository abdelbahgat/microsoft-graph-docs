---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new UnifiedGroupSource();
$group = new Group();
$group->setMail('SecretGroup@contoso.com');
$requestBody->setGroup($group);
$requestBody->setIncludedSources(new SourceType('mailbox, site'));

$result = $graphServiceClient->compliance()->ediscovery()->cases()->byCaseId('case-id')->custodians()->byCustodianId('custodian-id')->unifiedGroupSources()->post($requestBody)->wait();

```