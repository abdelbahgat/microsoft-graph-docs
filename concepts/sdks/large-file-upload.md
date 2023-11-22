---
title: "Upload large files using the Microsoft Graph SDKs"
description: "Provides guidance for uploading large files using the Microsoft Graph SDKs."
ms.localizationpriority: medium
author: DarrelMiller
---

<!-- markdownlint-disable MD024 MD051 -->

# Upload large files using the Microsoft Graph SDKs

A number of entities in Microsoft Graph support [resumable file uploads](/graph/api/driveitem-createuploadsession?view=graph-rest-1.0&preserve-view=true) to make it easier to upload large files. Instead of trying to upload the entire file in a single request, the file is sliced into smaller pieces and a request is used to upload a single slice. In order to simplify this process, the Microsoft Graph SDKs implement a large file upload task that manages the uploading of the slices.

## Upload large file to OneDrive

## [C#](#tab/csharp)

:::code language="csharp" source="./snippets/dotnet/src/SdkSnippets/Snippets/LargeFileUpload.cs" id="LargeFileUploadSnippet":::

## [Java](#tab/java)

:::code language="java" source="./snippets/java/app/src/main/java/snippets/LargeFileUpload.java" id="LargeFileUploadSnippet":::

## [PHP](#tab/PHP)

```php
<?php

// create a file stream
$file = Utils::streamFor(fopen('fileName', 'r'));

// create an upload session
$attachmentItem = new AttachmentItem();
$attachmentItem->setAttachmentType(new AttachmentType('file'));
$attachmentItem->setName('fileName');
$attachmentItem->setSize($file->getSize());

$uploadSessionRequestBody = new CreateUploadSessionPostRequestBody();
$uploadSessionRequestBody->setAttachmentItem($attachmentItem);

/** @var UploadSession $uploadSession */
$uploadSession = $graphServiceClient->users()->byUserId(USER_ID)->messages()->byMessageId('[id]')->attachments()->createUploadSession()->post($uploadSessionRequestBody)->wait();

// upload
$largeFileUpload = new LargeFileUploadTask($uploadSession, $graphServiceClient->getRequestAdapter(), $file);
try{
    $uploadSession = $largeFileUpload->upload()->wait();
} catch (\Psr\Http\Client\NetworkExceptionInterface $ex) {
    // resume upload in case of network errors
    $uploadSession = $largeFileUpload->resume()->wait();
}

```

## [TypeScript](#tab/typescript)

:::code language="typescript" source="./snippets/typescript/src/snippets/largeFileUpload.ts" id="LargeFileUploadSnippet":::


---

## Resuming a file upload

The Microsoft Graph SDKs support [resuming in-progress uploads](/graph/api/driveitem-createuploadsession?view=graph-rest-1.0&preserve-view=true#resuming-an-in-progress-upload). If your application encounters a connection interruption or a 5.x.x HTTP status during upload, you can resume the upload.

### [C#](#tab/csharp)

:::code language="csharp" source="./snippets/dotnet/src/SdkSnippets/Snippets/LargeFileUpload.cs" id="ResumeSnippet":::

### [Java](#tab/java)

> [!NOTE]
> The Java SDK does not currently support resuming in-progress downloads.

### [TypeScript](#tab/typescript)

:::code language="typescript" source="./snippets/typescript/src/snippets/largeFileUpload.ts" id="ResumeSnippet":::

---

## Upload large attachment to Outlook message

### [C#](#tab/csharp)

:::code language="csharp" source="./snippets/dotnet/src/SdkSnippets/Snippets/LargeFileUpload.cs" id="UploadAttachmentSnippet":::

### [Java](#tab/java)

:::code language="java" source="./snippets/java/app/src/main/java/snippets/LargeFileUpload.java" id="UploadAttachmentSnippet":::

### [PHP](#tab/PHP)

```php
<?php

// create a file stream
$file = Utils::streamFor(fopen('fileName', 'r'));

// create an upload session
$attachmentItem = new AttachmentItem();
$attachmentItem->setAttachmentType(new AttachmentType('file'));
$attachmentItem->setName('fileName');
$attachmentItem->setSize($file->getSize());

$uploadSessionRequestBody = new CreateUploadSessionPostRequestBody();
$uploadSessionRequestBody->setAttachmentItem($attachmentItem);

/** @var UploadSession $uploadSession */
$uploadSession = $graphServiceClient->users()->byUserId(USER_ID)->messages()->byMessageId('[id]')->attachments()->createUploadSession()->post($uploadSessionRequestBody)->wait();

// upload
$largeFileUpload = new LargeFileUploadTask($uploadSession, $graphServiceClient->getRequestAdapter(), $file);
try{
    $uploadSession = $largeFileUpload->upload()->wait();
} catch (\Psr\Http\Client\NetworkExceptionInterface $ex) {
    // resume upload in case of network errors
    $uploadSession = $largeFileUpload->resume()->wait();
}

// You can also cancel the session
//$largeFileUpload->cancel()->wait();

```

### [TypeScript](#tab/typescript)

:::code language="typescript" source="./snippets/typescript/src/snippets/largeFileUpload.ts" id="UploadAttachmentSnippet":::

---

<!-- markdownlint-enable MD024 -->
