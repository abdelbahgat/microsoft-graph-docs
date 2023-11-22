---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AppManagementPolicy();
$requestBody->setDisplayName('Credential management policy');
$requestBody->setDescription('Cred policy sample');
$requestBody->setIsEnabled(true);
$restrictions = new AppManagementConfiguration();
$passwordCredentialsPasswordCredentialConfiguration1 = new PasswordCredentialConfiguration();
$passwordCredentialsPasswordCredentialConfiguration1->setRestrictionType(new AppCredentialRestrictionType('passwordAddition'));
$passwordCredentialsPasswordCredentialConfiguration1->setMaxLifetime(null);
$passwordCredentialsPasswordCredentialConfiguration1->setRestrictForAppsCreatedAfterDateTime(new \DateTime('2019-10-19T10:37:00Z'));
$passwordCredentialsArray []= $passwordCredentialsPasswordCredentialConfiguration1;
$passwordCredentialsPasswordCredentialConfiguration2 = new PasswordCredentialConfiguration();
$passwordCredentialsPasswordCredentialConfiguration2->setRestrictionType(new AppCredentialRestrictionType('passwordLifetime'));
$passwordCredentialsPasswordCredentialConfiguration2->setMaxLifetime(new \DateInterval('P90D'));
$passwordCredentialsPasswordCredentialConfiguration2->setRestrictForAppsCreatedAfterDateTime(new \DateTime('2014-10-19T10:37:00Z'));
$passwordCredentialsArray []= $passwordCredentialsPasswordCredentialConfiguration2;
$passwordCredentialsPasswordCredentialConfiguration3 = new PasswordCredentialConfiguration();
$passwordCredentialsPasswordCredentialConfiguration3->setRestrictionType(new AppCredentialRestrictionType('symmetricKeyAddition'));
$passwordCredentialsPasswordCredentialConfiguration3->setMaxLifetime(null);
$passwordCredentialsPasswordCredentialConfiguration3->setRestrictForAppsCreatedAfterDateTime(new \DateTime('2019-10-19T10:37:00Z'));
$passwordCredentialsArray []= $passwordCredentialsPasswordCredentialConfiguration3;
$passwordCredentialsPasswordCredentialConfiguration4 = new PasswordCredentialConfiguration();
$passwordCredentialsPasswordCredentialConfiguration4->setRestrictionType(new AppCredentialRestrictionType('symmetricKeyLifetime'));
$passwordCredentialsPasswordCredentialConfiguration4->setMaxLifetime(new \DateInterval('P30D'));
$passwordCredentialsPasswordCredentialConfiguration4->setRestrictForAppsCreatedAfterDateTime(new \DateTime('2014-10-19T10:37:00Z'));
$passwordCredentialsArray []= $passwordCredentialsPasswordCredentialConfiguration4;
$restrictions->setPasswordCredentials($passwordCredentialsArray);

$keyCredentialsKeyCredentialConfiguration1 = new KeyCredentialConfiguration();
$keyCredentialsKeyCredentialConfiguration1->setRestrictionType(new AppKeyCredentialRestrictionType('asymmetricKeyLifetime'));
$keyCredentialsKeyCredentialConfiguration1->setMaxLifetime(new \DateInterval('P90D'));
$keyCredentialsKeyCredentialConfiguration1->setRestrictForAppsCreatedAfterDateTime(new \DateTime('2014-10-19T10:37:00Z'));
$keyCredentialsArray []= $keyCredentialsKeyCredentialConfiguration1;
$keyCredentialsKeyCredentialConfiguration2 = new KeyCredentialConfiguration();
$keyCredentialsKeyCredentialConfiguration2->setRestrictionType(new AppKeyCredentialRestrictionType('trustedCertificateAuthority'));
$keyCredentialsKeyCredentialConfiguration2->setRestrictForAppsCreatedAfterDateTime(new \DateTime('2019-10-19T10:37:00Z'));
$keyCredentialsKeyCredentialConfiguration2->setCertificateBasedApplicationConfigurationIds(['eec5ba11-2fc0-4113-83a2-ed986ed13743', 'bb8e164b-f9ed-4b98-bc45-65eddc14f4c1', ]);
$keyCredentialsKeyCredentialConfiguration2->setMaxLifetime(null);
$keyCredentialsArray []= $keyCredentialsKeyCredentialConfiguration2;
$restrictions->setKeyCredentials($keyCredentialsArray);

$requestBody->setRestrictions($restrictions);

$result = $graphServiceClient->policies()->appManagementPolicies()->post($requestBody)->wait();

```