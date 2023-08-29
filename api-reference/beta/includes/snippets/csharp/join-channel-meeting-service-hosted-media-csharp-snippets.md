---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var call = new Call
{
	CallbackUri = "https://bot.contoso.com/callback",
	RequestedModalities = new List<Modality>()
	{
		Modality.Audio
	},
	MediaConfig = new ServiceHostedMediaConfig
	{
		PreFetchMedia = new List<MediaInfo>()
		{
			new MediaInfo
			{
				Uri = "https://cdn.contoso.com/beep.wav",
				ResourceId = "f8971b04-b53e-418c-9222-c82ce681a582"
			},
			new MediaInfo
			{
				Uri = "https://cdn.contoso.com/cool.wav",
				ResourceId = "86dc814b-c172-4428-9112-60f8ecae1edb"
			}
		}
	},
	ChatInfo = new ChatInfo
	{
		ThreadId = "19:cbee7c1c860e465f8258e3cebf7bee0d@thread.skype",
		MessageId = "1533758867081"
	},
	MeetingInfo = new OrganizerMeetingInfo
	{
		Organizer = new IdentitySet
		{
			User = new Identity
			{
				Id = "5810cede-f3cc-42eb-b2c1-e9bd5d53ec96",
				TenantId = "aa67bd4c-8475-432d-bd41-39f255720e0a",
				DisplayName = "Bob"
			}
		},
		AllowConversationWithoutHost = true
	}
};

await graphClient.Communications.Calls
	.Request()
	.AddAsync(call);

```