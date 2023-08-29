---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new CreateUploadSessionPostRequestBody();
$attachmentItem = new AttachmentItem();
$attachmentItem->setAttachmentType(new AttachmentType('file'));

$attachmentItem->setName('flower');

$attachmentItem->setSize(size);


$requestBody->setAttachmentItem($attachmentItem);


$requestResult = $graphServiceClient->me()->messagesById('message-id')->attachments()->createUploadSession()->post($requestBody);


```