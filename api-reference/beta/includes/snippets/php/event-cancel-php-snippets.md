---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new CancelPostRequestBody();
$requestBody->setComment('Cancelling for this week due to all hands');



$graphServiceClient->me()->eventsById('event-id')->cancel()->post($requestBody);


```