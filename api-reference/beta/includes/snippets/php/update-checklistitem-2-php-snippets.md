---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new ChecklistItem();
$requestBody->setDisplayName('buy cake');



$graphServiceClient->me()->tasks()->listsById('baseTaskList-id')->tasksById('baseTask-id')->checklistItemsById('checklistItem-id')->patch($requestBody);


```