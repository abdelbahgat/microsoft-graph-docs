---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ProjectParticipation();
$requestBody->setAllowedAudiences(new AllowedAudiences('organization'));
$client = new CompanyDetail();
$client->setDepartment('Corporate Marketing');
$client->setWebUrl('https://www.contoso.com');
$requestBody->setClient($client);

$result = $graphServiceClient->me()->profile()->projects()->byProjectParticipationId('projectParticipation-id')->patch($requestBody)->wait();

```