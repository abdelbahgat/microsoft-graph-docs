---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CreateUploadSessionPostRequestBody();
$properties = new PrintDocumentUploadProperties();
$properties->setDocumentName('TestFile.pdf');
$properties->setContentType('application/pdf');
$properties->setSize(4533322);
$requestBody->setProperties($properties);

$result = $graphServiceClient->escapedPrint()->shares()->byPrinterShareId('printerShare-id')->jobs()->byPrintJobId('printJob-id')->documents()->byPrintDocumentId('printDocument-id')->createUploadSession()->post($requestBody)->wait();

```