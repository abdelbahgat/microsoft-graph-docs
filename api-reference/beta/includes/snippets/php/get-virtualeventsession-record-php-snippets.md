---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);


$result = $graphServiceClient->solutions()->virtualEvents()->webinars()->byVirtualEventWebinarId('virtualEventWebinar-id')->sessions()->byVirtualEventSessionId('virtualEventSession-id')->attendanceReports()->byMeetingAttendanceReportId('meetingAttendanceReport-id')->attendanceRecords()->get()->wait();

```