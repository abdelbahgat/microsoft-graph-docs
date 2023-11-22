---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new PersonAnnotation();
$requestBody->setAllowedAudiences(new AllowedAudiences('organization'));

$result = $graphServiceClient->users()->byUserId('user-id')->profile()->notes()->byPersonAnnotationId('personAnnotation-id')->patch($requestBody)->wait();

```