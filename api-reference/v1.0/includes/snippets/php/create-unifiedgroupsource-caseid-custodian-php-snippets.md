---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new UnifiedGroupSource();
$group = new Group();
$group->setMail('SOCTeam@M365x809305.onmicrosoft.com');


$requestBody->setGroup($group);
$requestBody->setIncludedSources(new SourceType('mailbox, site'));



$result = $graphServiceClient->security()->cases()->ediscoveryCasesById('ediscoveryCase-id')->custodiansById('ediscoveryCustodian-id')->unifiedGroupSources()->post($requestBody);


```