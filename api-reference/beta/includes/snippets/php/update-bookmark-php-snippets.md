---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new Bookmark();
$requestBody->setDescription('Book a fancy vacation in Tuscany or browse museums in Florence.');



$graphServiceClient->search()->bookmarksById('bookmark-id')->patch($requestBody);


```