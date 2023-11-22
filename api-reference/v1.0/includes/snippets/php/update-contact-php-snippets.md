---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Contact();
$homeAddress = new PhysicalAddress();
$homeAddress->setStreet('123 Some street');
$homeAddress->setCity('Seattle');
$homeAddress->setState('WA');
$homeAddress->setPostalCode('98121');
$requestBody->setHomeAddress($homeAddress);
$requestBody->setBirthday(new \DateTime('1974-07-22'));

$result = $graphServiceClient->me()->contacts()->byContactId('contact-id')->patch($requestBody)->wait();

```