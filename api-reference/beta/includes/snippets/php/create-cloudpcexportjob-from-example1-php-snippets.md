---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CloudPcExportJob();
$requestBody->setReportName(new CloudPcReportName('totalAggregatedRemoteConnectionReports'));
$requestBody->setSelect(['CloudPcId', 'ManagedDeviceName', 'UserPrincipalName', 'DaysSinceLastSignIn', 'TotalUsageInHour', 	]);

$result = $graphServiceClient->deviceManagement()->virtualEndpoint()->reports()->exportJobs()->post($requestBody)->wait();

```