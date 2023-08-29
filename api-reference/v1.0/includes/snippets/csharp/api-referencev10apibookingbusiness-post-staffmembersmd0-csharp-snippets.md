---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var bookingStaffMemberBase = new BookingStaffMember
{
	DisplayName = "Dana Swope",
	EmailAddress = "danas@contoso.com",
	Role = BookingStaffRole.ExternalGuest,
	TimeZone = "America/Chicago",
	UseBusinessHours = true,
	WorkingHours = new List<BookingWorkHours>()
	{
		new BookingWorkHours
		{
			Day = DayOfWeek.Monday,
			TimeSlots = new List<BookingWorkTimeSlot>()
			{
				new BookingWorkTimeSlot
				{
					EndTime = new TimeOfDay(17, 0, 0),
					StartTime = new TimeOfDay(8, 0, 0)
				}
			},
			AdditionalData = new Dictionary<string, object>()
			{
				{"day@odata.type", "#microsoft.graph.dayOfWeek"},
				{"timeSlots@odata.type", "#Collection(microsoft.graph.bookingWorkTimeSlot)"}
			}
		},
		new BookingWorkHours
		{
			Day = DayOfWeek.Tuesday,
			TimeSlots = new List<BookingWorkTimeSlot>()
			{
				new BookingWorkTimeSlot
				{
					EndTime = new TimeOfDay(17, 0, 0),
					StartTime = new TimeOfDay(8, 0, 0)
				}
			},
			AdditionalData = new Dictionary<string, object>()
			{
				{"day@odata.type", "#microsoft.graph.dayOfWeek"},
				{"timeSlots@odata.type", "#Collection(microsoft.graph.bookingWorkTimeSlot)"}
			}
		},
		new BookingWorkHours
		{
			Day = DayOfWeek.Wednesday,
			TimeSlots = new List<BookingWorkTimeSlot>()
			{
				new BookingWorkTimeSlot
				{
					EndTime = new TimeOfDay(17, 0, 0),
					StartTime = new TimeOfDay(8, 0, 0)
				}
			},
			AdditionalData = new Dictionary<string, object>()
			{
				{"day@odata.type", "#microsoft.graph.dayOfWeek"},
				{"timeSlots@odata.type", "#Collection(microsoft.graph.bookingWorkTimeSlot)"}
			}
		},
		new BookingWorkHours
		{
			Day = DayOfWeek.Thursday,
			TimeSlots = new List<BookingWorkTimeSlot>()
			{
				new BookingWorkTimeSlot
				{
					EndTime = new TimeOfDay(17, 0, 0),
					StartTime = new TimeOfDay(8, 0, 0)
				}
			},
			AdditionalData = new Dictionary<string, object>()
			{
				{"day@odata.type", "#microsoft.graph.dayOfWeek"},
				{"timeSlots@odata.type", "#Collection(microsoft.graph.bookingWorkTimeSlot)"}
			}
		},
		new BookingWorkHours
		{
			Day = DayOfWeek.Friday,
			TimeSlots = new List<BookingWorkTimeSlot>()
			{
				new BookingWorkTimeSlot
				{
					EndTime = new TimeOfDay(17, 0, 0),
					StartTime = new TimeOfDay(8, 0, 0)
				}
			},
			AdditionalData = new Dictionary<string, object>()
			{
				{"day@odata.type", "#microsoft.graph.dayOfWeek"},
				{"timeSlots@odata.type", "#Collection(microsoft.graph.bookingWorkTimeSlot)"}
			}
		}
	},
	AdditionalData = new Dictionary<string, object>()
	{
		{"role@odata.type", "#microsoft.graph.bookingStaffRole"},
		{"workingHours@odata.type", "#Collection(microsoft.graph.bookingWorkHours)"}
	}
};

await graphClient.Solutions.BookingBusinesses["{bookingBusiness-id}"].StaffMembers
	.Request()
	.AddAsync(bookingStaffMemberBase);

```