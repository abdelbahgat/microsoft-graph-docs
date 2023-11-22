---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new PrinterShare();
$requestBody->setDisplayName('PrinterShare Name');
$requestBody->setAllowAllUsers(false);
$additionalData = [
	'printer@odata.bind' => 'https://graph.microsoft.com/v1.0/print/printers/{printerId}',
];
$requestBody->setAdditionalData($additionalData);

$result = $graphServiceClient->escapedPrint()->shares()->byPrinterShareId('printerShare-id')->patch($requestBody)->wait();

```