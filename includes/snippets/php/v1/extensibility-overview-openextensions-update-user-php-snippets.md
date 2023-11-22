---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Extension();
$additionalData = [
	'xboxGamerTag' => 'FierceAdele',
	'linkedInProfile' => 'www.linkedin.com/in/testlinkedinprofile',
];
$requestBody->setAdditionalData($additionalData);

$result = $graphServiceClient->users()->byUserId('user-id')->extensions()->byExtensionId('extension-id')->patch($requestBody)->wait();

```