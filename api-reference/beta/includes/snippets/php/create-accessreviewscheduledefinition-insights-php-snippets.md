---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AccessReviewScheduleDefinition();
$requestBody->setDisplayName('Test create');
$requestBody->setDescriptionForAdmins('New scheduled access review');
$requestBody->setDescriptionForReviewers('If you have any questions, contact jerry@contoso.com');
$scope = new AccessReviewQueryScope();
$scope->setOdataType('#microsoft.graph.accessReviewQueryScope');
$scope->setQuery('/groups/02f3bafb-448c-487c-88c2-5fd65ce49a41/transitiveMembers');
$scope->setQueryType('MicrosoftGraph');
$requestBody->setScope($scope);
$reviewersAccessReviewReviewerScope1 = new AccessReviewReviewerScope();
$reviewersAccessReviewReviewerScope1->setQuery('/users/398164b1-5196-49dd-ada2-364b49f99b27');
$reviewersAccessReviewReviewerScope1->setQueryType('MicrosoftGraph');
$reviewersArray []= $reviewersAccessReviewReviewerScope1;
$requestBody->setReviewers($reviewersArray);

$settings = new AccessReviewScheduleSettings();
$settings->setInstanceDurationInDays(1);
$settingsRecurrence = new PatternedRecurrence();
$settingsRecurrencePattern = new RecurrencePattern();
$settingsRecurrencePattern->setType(new RecurrencePatternType('weekly'));
$settingsRecurrencePattern->setInterval(1);
$settingsRecurrence->setPattern($settingsRecurrencePattern);
$settingsRecurrenceRange = new RecurrenceRange();
$settingsRecurrenceRange->setType(new RecurrenceRangeType('noEnd'));
$settingsRecurrenceRange->setStartDate(new Date('2020-09-08T12:02:30.667Z'));
$settingsRecurrence->setRange($settingsRecurrenceRange);
$settings->setRecurrence($settingsRecurrence);
$recommendationInsightSettingsAccessReviewRecommendationInsightSetting1 = new UserLastSignInRecommendationInsightSetting();
$recommendationInsightSettingsAccessReviewRecommendationInsightSetting1->setOdataType('#microsoft.graph.userLastSignInRecommendationInsightSetting');
$recommendationInsightSettingsAccessReviewRecommendationInsightSetting1->setRecommendationLookBackDuration(new \DateInterval('P30D'));
$recommendationInsightSettingsAccessReviewRecommendationInsightSetting1->setSignInScope(new UserSignInRecommendationScope('tenant'));
$recommendationInsightSettingsArray []= $recommendationInsightSettingsAccessReviewRecommendationInsightSetting1;
$recommendationInsightSettingsAccessReviewRecommendationInsightSetting2 = new GroupPeerOutlierRecommendationInsightSettings();
$recommendationInsightSettingsAccessReviewRecommendationInsightSetting2->setOdataType('#microsoft.graph.groupPeerOutlierRecommendationInsightSettings');
$recommendationInsightSettingsArray []= $recommendationInsightSettingsAccessReviewRecommendationInsightSetting2;
$settings->setRecommendationInsightSettings($recommendationInsightSettingsArray);

$requestBody->setSettings($settings);

$result = $graphServiceClient->identityGovernance()->accessReviews()->definitions()->post($requestBody)->wait();

```