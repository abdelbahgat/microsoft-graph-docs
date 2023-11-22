---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Permission();
$requestBody->setRoles(['write', 	]);
$grantedToIdentitiesIdentitySet1 = new IdentitySet();
$grantedToIdentitiesIdentitySet1Application = new Identity();
$grantedToIdentitiesIdentitySet1Application->setId('89ea5c94-7736-4e25-95ad-3fa95f62b66e');
$grantedToIdentitiesIdentitySet1Application->setDisplayName('Contoso Time Manager App');
$grantedToIdentitiesIdentitySet1->setApplication($grantedToIdentitiesIdentitySet1Application);
$grantedToIdentitiesArray []= $grantedToIdentitiesIdentitySet1;
$requestBody->setGrantedToIdentities($grantedToIdentitiesArray);


$result = $graphServiceClient->sites()->bySiteId('site-id')->permissions()->post($requestBody)->wait();

```