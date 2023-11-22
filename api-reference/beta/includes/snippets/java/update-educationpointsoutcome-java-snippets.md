---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

EducationPointsOutcome educationOutcome = new EducationPointsOutcome();
EducationAssignmentPointsGrade points = new EducationAssignmentPointsGrade();
points.points = 85.0;
educationOutcome.points = points1;

graphClient.education().classes("{id}").assignments("{id}").submissions("{id}").outcomes("{id}")
	.buildRequest()
	.patch(educationOutcome);

```