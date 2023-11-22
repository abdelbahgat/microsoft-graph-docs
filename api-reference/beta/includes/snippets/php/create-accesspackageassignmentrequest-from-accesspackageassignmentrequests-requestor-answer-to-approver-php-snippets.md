---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AccessPackageAssignmentRequest();
$requestBody->setRequestType('UserAdd');
$accessPackageAssignment = new AccessPackageAssignment();
$accessPackageAssignment->setTargetId('46184453-e63b-4f20-86c2-c557ed5d5df9');
$accessPackageAssignment->setAssignmentPolicyId('2264bf65-76ba-417b-a27d-54d291f0cbc8');
$accessPackageAssignment->setAccessPackageId('a914b616-e04e-476b-aa37-91038f0b165b');
$requestBody->setAccessPackageAssignment($accessPackageAssignment);
$answersAccessPackageAnswer1 = new AccessPackageAnswerString();
$answersAccessPackageAnswer1->setOdataType('#microsoft.graph.accessPackageAnswerString');
$answersAccessPackageAnswer1->setValue('Arizona');
$answersAccessPackageAnswer1AnsweredQuestion = new AccessPackageMultipleChoiceQuestion();
$answersAccessPackageAnswer1AnsweredQuestion->setOdataType('#microsoft.graph.accessPackageMultipleChoiceQuestion');
$answersAccessPackageAnswer1AnsweredQuestion->setId('A714EC6F-4EE0-4614-BD81-37E0C5ECBBFF');
$answersAccessPackageAnswer1->setAnsweredQuestion($answersAccessPackageAnswer1AnsweredQuestion);
$answersArray []= $answersAccessPackageAnswer1;
$answersAccessPackageAnswer2 = new AccessPackageAnswerString();
$answersAccessPackageAnswer2->setOdataType('#microsoft.graph.accessPackageAnswerString');
$answersAccessPackageAnswer2->setValue('Need access to marketing campaign material');
$answersAccessPackageAnswer2AnsweredQuestion = new AccessPackageTextInputQuestion();
$answersAccessPackageAnswer2AnsweredQuestion->setOdataType('#microsoft.graph.accessPackageTextInputQuestion');
$answersAccessPackageAnswer2AnsweredQuestion->setId('AA615EE9-D9D8-4C03-BE91-BEE37106DEDA');
$answersAccessPackageAnswer2->setAnsweredQuestion($answersAccessPackageAnswer2AnsweredQuestion);
$answersArray []= $answersAccessPackageAnswer2;
$requestBody->setAnswers($answersArray);


$result = $graphServiceClient->identityGovernance()->entitlementManagement()->accessPackageAssignmentRequests()->post($requestBody)->wait();

```