---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const sendActivityNotification = {
    topic: {
        source: 'entityUrl',
        value: 'https://graph.microsoft.com/beta/teams/e8bece96-d393-4b9b-b8da-69cedef1a7e7'
    },
    activityType: 'pendingFinanceApprovalRequests',
    previewText: {
        content: 'Internal spending team has a pending finance approval requests'
    },
    recipient: {
        '@odata.type': 'microsoft.graph.channelMembersNotificationRecipient',
        teamId: 'e8bece96-d393-4b9b-b8da-69cedef1a7e7',
        channelId: '19:3d61a2309f094f4a9310b20f1db37520@thread.tacv2'
    },
    templateParameters: [
        {
            name: 'pendingRequestCount',
            value: '5'
        }
    ] 
};

await client.api('/teams/e8bece96-d393-4b9b-b8da-69cedef1a7e7/sendActivityNotification')
	.version('beta')
	.post(sendActivityNotification);

```