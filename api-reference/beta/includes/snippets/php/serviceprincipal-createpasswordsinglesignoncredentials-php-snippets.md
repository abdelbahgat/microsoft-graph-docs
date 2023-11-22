---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CreatePasswordSingleSignOnCredentialsPostRequestBody();
$requestBody->setId('5793aa3b-cca9-4794-679a240f8b58');
$credentialsCredential1 = new Credential();
$credentialsCredential1->setFieldId('param_username');
$credentialsCredential1->setValue('myusername');
$credentialsCredential1->setType('username');
$credentialsArray []= $credentialsCredential1;
$credentialsCredential2 = new Credential();
$credentialsCredential2->setFieldId('param_password');
$credentialsCredential2->setValue('pa$$w0rd');
$credentialsCredential2->setType('password');
$credentialsArray []= $credentialsCredential2;
$requestBody->setCredentials($credentialsArray);


$result = $graphServiceClient->servicePrincipals()->byServicePrincipalId('servicePrincipal-id')->createPasswordSingleSignOnCredentials()->post($requestBody)->wait();

```