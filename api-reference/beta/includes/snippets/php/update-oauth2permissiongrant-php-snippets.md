---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new OAuth2PermissionGrant();
$requestBody->setScope('User.ReadBasic.All Group.ReadWrite.All');



$graphServiceClient->oauth2PermissionGrantsById('oAuth2PermissionGrant-id')->patch($requestBody);


```