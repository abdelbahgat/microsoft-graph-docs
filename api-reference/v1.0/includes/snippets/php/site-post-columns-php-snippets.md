---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new ColumnDefinition();
$requestBody->setDescription('test');

$requestBody->setEnforceUniqueValues(false);

$requestBody->setHidden(false);

$requestBody->setIndexed(false);

$requestBody->setName('Title');

$text = new TextColumn();
$text->setAllowMultipleLines(false);

$text->setAppendChangesToExistingText(false);

$text->setLinesForEditing(linesForEditing);

$text->setMaxLength(maxLength);


$requestBody->setText($text);


$requestResult = $graphServiceClient->sitesById('site-id')->columns()->post($requestBody);


```