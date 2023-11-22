---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AlertRule();
$requestBody->setId('215c55cc-b1c9-4d36-a870-be5778101714');
$requestBody->setDisplayName('Azure network connection failure impacting Cloud PCs');
$requestBody->setSeverity(new RuleSeverityType('informational'));
$requestBody->setIsSystemRule(true);
$requestBody->setDescription('Azure network connection checks have failed and is potentially impacting existing Cloud PCs and blocking the provisioning of new Cloud PCs');
$requestBody->setEnabled(true);
$requestBody->setAlertRuleTemplate(new AlertRuleTemplate('cloudPcOnPremiseNetworkConnectionCheckScenario'));
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

$result = $graphServiceClient->deviceManagement()->monitoring()->alertRules()->post($requestBody)->wait();

```