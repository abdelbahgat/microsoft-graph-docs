---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new MarkUnreadPostRequestBody();
$requestBody->setMessageIds(['MC172851', 'MC167983', ]);



$requestResult = $graphServiceClient->admin()->serviceAnnouncement()->messages()->markUnread()->post($requestBody);


```