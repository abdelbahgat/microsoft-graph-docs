---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new InstantiatePostRequestBody();
$requestBody->setDisplayName('Azure AD SAML Toolkit');

$result = $graphServiceClient->applicationTemplates()->byApplicationTemplateId('applicationTemplate-id')->instantiate()->post($requestBody)->wait();

```