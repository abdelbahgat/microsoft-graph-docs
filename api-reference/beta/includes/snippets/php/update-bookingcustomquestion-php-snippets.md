---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new BookingCustomQuestion();
$requestBody->setOdataType('#microsoft.graph.bookingCustomQuestion');
$requestBody->setDisplayName('What is your age?');
$requestBody->setAnswerInputType(new AnswerInputType('text'));
$requestBody->setAnswerOptions([	]);

$result = $graphServiceClient->bookingBusinesses()->byBookingBusinessId('bookingBusiness-id')->customQuestions()->byBookingCustomQuestionId('bookingCustomQuestion-id')->patch($requestBody)->wait();

```