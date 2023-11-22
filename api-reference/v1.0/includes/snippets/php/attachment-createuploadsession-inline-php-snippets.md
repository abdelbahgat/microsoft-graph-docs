---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CreateUploadSessionPostRequestBody();
$attachmentItem = new AttachmentItem();
$attachmentItem->setAttachmentType(new AttachmentType('file'));
$attachmentItem->setName('scenary');
$attachmentItem->setSize(7208534);
$attachmentItem->setIsInline(true);
$attachmentItem->setContentId('my_inline_picture');
$requestBody->setAttachmentItem($attachmentItem);

$result = $graphServiceClient->me()->messages()->byMessageId('message-id')->attachments()->createUploadSession()->post($requestBody)->wait();

```