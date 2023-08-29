---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new CreateUploadSessionPostRequestBody();
$attachmentInfo = new AttachmentInfo();
$attachmentInfo->set@odatatype('microsoft.graph.attachmentInfo');

$attachmentInfo->setAttachmentType(new AttachmentType('file'));

$attachmentInfo->setName('flower');

$attachmentInfo->setSize(size);


$requestBody->setAttachmentInfo($attachmentInfo);


$requestResult = $graphServiceClient->me()->todo()->listsById('todoTaskList-id')->tasksById('todoTask-id')->attachments()->createUploadSession()->post($requestBody);


```