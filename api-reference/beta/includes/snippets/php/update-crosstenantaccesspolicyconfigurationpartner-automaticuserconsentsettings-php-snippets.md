---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CrossTenantAccessPolicyConfigurationPartner();
$automaticUserConsentSettings = new InboundOutboundPolicyConfiguration();
$automaticUserConsentSettings->setInboundAllowed(true);
$automaticUserConsentSettings->setOutboundAllowed(true);
$requestBody->setAutomaticUserConsentSettings($automaticUserConsentSettings);

$result = $graphServiceClient->policies()->crossTenantAccessPolicy()->partners()->byCrossTenantAccessPolicyConfigurationPartnerTenantId('crossTenantAccessPolicyConfigurationPartner-tenantId')->patch($requestBody)->wait();

```