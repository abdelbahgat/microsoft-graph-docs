---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AlertRule();
$requestBody->setSeverity(new RuleSeverityType('informational'));
$requestBody->setEnabled(true);
$threshold = new RuleThreshold();
$threshold->setAggregation(new AggregationType('count'));
$threshold->setOperator(new OperatorType('greaterOrEqual'));
$threshold->setTarget(90);
$requestBody->setThreshold($threshold);
$notificationChannelsNotificationChannel1 = new NotificationChannel();
$notificationChannelsNotificationChannel1->setNotificationChannelType(new NotificationChannelType('portal'));
$notificationChannelsNotificationChannel1->setNotificationReceivers([	]);
$notificationChannelsArray []= $notificationChannelsNotificationChannel1;
$notificationChannelsNotificationChannel2 = new NotificationChannel();
$notificationChannelsNotificationChannel2->setNotificationChannelType(new NotificationChannelType('email'));
$notificationReceiversNotificationReceiver1 = new NotificationReceiver();
$notificationReceiversNotificationReceiver1->setLocale('en-us');
$notificationReceiversNotificationReceiver1->setContactInformation('serena.davis@contoso.com');
$notificationReceiversArray []= $notificationReceiversNotificationReceiver1;
$notificationChannelsNotificationChannel2->setNotificationReceivers($notificationReceiversArray);

$notificationChannelsArray []= $notificationChannelsNotificationChannel2;
$requestBody->setNotificationChannels($notificationChannelsArray);

$additionalData = [
'conditions' => [
	[
		'relationshipType' => 'or',
		'conditionCategory' => 'azureNetworkConnectionCheckFailures',
		'aggregation' => 'count',
		'operator' => 'greaterOrEqual',
		'thresholdValue' => '90',
	],
],
];
$requestBody->setAdditionalData($additionalData);

$result = $graphServiceClient->deviceManagement()->monitoring()->alertRules()->byAlertRuleId('alertRule-id')->patch($requestBody)->wait();

```