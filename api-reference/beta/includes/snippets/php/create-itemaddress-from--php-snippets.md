---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ItemAddress();
$requestBody->setDisplayName('Home');
$detail = new PhysicalAddress();
$detail->setType(new PhysicalAddressType('home'));
$detail->setPostOfficeBox(null);
$detail->setStreet('221B Baker Street');
$detail->setCity('London');
$detail->setState(null);
$detail->setCountryOrRegion('United Kingdom');
$detail->setPostalCode('E14 3TD');
$requestBody->setDetail($detail);

$result = $graphServiceClient->me()->profile()->addresses()->post($requestBody)->wait();

```