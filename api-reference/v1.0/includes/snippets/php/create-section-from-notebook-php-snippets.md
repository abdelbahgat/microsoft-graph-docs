---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new OnenoteSection();
$requestBody->setDisplayName('Section name');



$requestResult = $graphServiceClient->me()->onenote()->notebooksById('notebook-id')->sections()->post($requestBody);


```