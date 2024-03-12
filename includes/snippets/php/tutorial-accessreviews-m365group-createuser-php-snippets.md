---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new User();
$requestBody->setAccountEnabled(true);

$requestBody->setDisplayName('Aline Dupuy');

$requestBody->setMailNickname('AlineD');

$requestBody->setUserPrincipalName('AlineD@contoso.com');

$passwordProfile = new PasswordProfile();
$passwordProfile->setForceChangePasswordNextSignIn(true);

$passwordProfile->setPassword('xWwvJ]6NMw+bWH-d');


$requestBody->setPasswordProfile($passwordProfile);


$result = $graphServiceClient->users()->post($requestBody);


```