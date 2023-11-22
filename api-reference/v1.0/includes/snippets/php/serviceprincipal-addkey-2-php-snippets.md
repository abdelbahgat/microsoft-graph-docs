---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AddKeyPostRequestBody();
$keyCredential = new KeyCredential();
$keyCredential->setType('X509CertAndPassword');
$keyCredential->setUsage('Sign');
$keyCredential->setKey(\GuzzleHttp\Psr7\Utils::streamFor(base64_decode('MIIDYDCCAki...')));
$requestBody->setKeyCredential($keyCredential);
$passwordCredential = new PasswordCredential();
$passwordCredential->setSecretText('MKTr0w1...');
$requestBody->setPasswordCredential($passwordCredential);
$requestBody->setProof('eyJ0eXAiOiJ...');

$result = $graphServiceClient->servicePrincipals()->byServicePrincipalId('servicePrincipal-id')->addKey()->post($requestBody)->wait();

```