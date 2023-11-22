---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Contact();
$requestBody->setParentFolderId('parentFolderId-value');
$requestBody->setBirthday(new \DateTime('datetime-value'));
$requestBody->setFileAs('fileAs-value');
$requestBody->setDisplayName('displayName-value');
$requestBody->setGivenName('givenName-value');
$requestBody->setInitials('initials-value');

$result = $graphServiceClient->me()->contactFolders()->byContactFolderId('contactFolder-id')->contacts()->post($requestBody)->wait();

```