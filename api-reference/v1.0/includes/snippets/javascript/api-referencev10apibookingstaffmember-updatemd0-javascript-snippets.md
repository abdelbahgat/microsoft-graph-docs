---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const bookingStaffMemberBase = {
    '@odata.type':'#microsoft.graph.bookingStaffMember',
    workingHours: [
        {
            '@odata.type':'#microsoft.graph.bookingWorkHours',
            'day@odata.type':'#microsoft.graph.dayOfWeek',
            day: 'monday',
            'timeSlots@odata.type':'#Collection(microsoft.graph.bookingWorkTimeSlot)',
            timeSlots: [

            ]
        },
        {
            '@odata.type':'#microsoft.graph.bookingWorkHours',
            'day@odata.type':'#microsoft.graph.dayOfWeek',
            day: 'tuesday',
            'timeSlots@odata.type':'#Collection(microsoft.graph.bookingWorkTimeSlot)',
            timeSlots: [
                {
                    '@odata.type':'#microsoft.graph.bookingWorkTimeSlot',
                    endTime: '17:00:00.0000000',
                    startTime: '08:00:00.0000000'
                }
            ]
        },
        {
            '@odata.type':'#microsoft.graph.bookingWorkHours',
            'day@odata.type':'#microsoft.graph.dayOfWeek',
            day: 'wednesday',
            'timeSlots@odata.type':'#Collection(microsoft.graph.bookingWorkTimeSlot)',
            timeSlots: [
                {
                    '@odata.type':'#microsoft.graph.bookingWorkTimeSlot',
                    endTime: '17:00:00.0000000',
                    startTime: '08:00:00.0000000'
                }
            ]
        },
        {
            '@odata.type':'#microsoft.graph.bookingWorkHours',
            'day@odata.type':'#microsoft.graph.dayOfWeek',
            day: 'thursday',
            'timeSlots@odata.type':'#Collection(microsoft.graph.bookingWorkTimeSlot)',
            timeSlots: [
                {
                    '@odata.type':'#microsoft.graph.bookingWorkTimeSlot',
                    endTime: '17:00:00.0000000',
                    startTime: '08:00:00.0000000'
                }
            ]
        },
        {
            '@odata.type':'#microsoft.graph.bookingWorkHours',
            'day@odata.type':'#microsoft.graph.dayOfWeek',
            day: 'friday',
            'timeSlots@odata.type':'#Collection(microsoft.graph.bookingWorkTimeSlot)',
            timeSlots: [
                {
                    '@odata.type':'#microsoft.graph.bookingWorkTimeSlot',
                    endTime: '17:00:00.0000000',
                    startTime: '08:00:00.0000000'
                }
            ]
        }
    ]
};

await client.api('/solutions/bookingBusinesses/Contosolunchdelivery@contoso.onmicrosoft.com/staffmembers/8ee1c803-a1fa-406d-8259-7ab53233f148')
	.update(bookingStaffMemberBase);

```