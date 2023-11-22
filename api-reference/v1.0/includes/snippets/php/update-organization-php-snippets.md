---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Organization();
$requestBody->setMarketingNotificationEmails(['marketing@contoso.com', 	]);
$privacyProfile = new PrivacyProfile();
$privacyProfile->setContactEmail('alice@contoso.com');
$privacyProfile->setStatementUrl('https://contoso.com/privacyStatement');
$requestBody->setPrivacyProfile($privacyProfile);
$requestBody->setSecurityComplianceNotificationMails(['security@contoso.com', 	]);
$requestBody->setSecurityComplianceNotificationPhones(['(123) 456-7890', 	]);
$requestBody->setTechnicalNotificationMails(['tech@contoso.com', 	]);

$result = $graphServiceClient->organization()->byOrganizationId('organization-id')->patch($requestBody)->wait();

```