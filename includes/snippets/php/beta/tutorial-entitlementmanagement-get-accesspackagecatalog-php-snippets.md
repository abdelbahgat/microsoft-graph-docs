---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new AccessPackageCatalogsRequestBuilderGetRequestConfiguration();
$queryParameters = AccessPackageCatalogsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->filter = "(displayName eq 'General')";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->identityGovernance()->entitlementManagement()->accessPackageCatalogs()->get($requestConfiguration)->wait();

```