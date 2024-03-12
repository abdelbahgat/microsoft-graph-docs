---
title: "Known issues with Microsoft Graph"
description: "This article describes known issues and limitations with Microsoft Graph and provides workarounds when possible."
author: "MSGraphDocsVTeam"
ms.localizationpriority: high
---

# Known issues with Microsoft Graph

This article describes known issues with Microsoft Graph. 

To report a known issue, see the [Microsoft Graph support](https://developer.microsoft.com/graph/support) page.

For information about the latest updates to the Microsoft Graph API, see the [Microsoft Graph changelog](changelog.md).

## Applications

### Some limitations apply to the application and servicePrincipal resources

Changes to the [application](/graph/api/resources/application) and [servicePrincipal](/graph/api/resources/serviceprincipal) resources are currently in development. The following is a summary of current limitations and in-development API features.

Current limitations:

- Some application properties (such as appRoles and addIns) will not be available until all changes are completed.
- Only multi-tenant apps can be registered.
- Updating apps is restricted to apps registered after the initial beta update.
- Azure Active Directory users can register apps and add additional owners.
- Support for OpenID Connect and OAuth protocols.
- Policy assignments to an application fail.
- Operations on ownedObjects that require appId fail (For example, users/{id|userPrincipalName}/ownedObjects/{id}/...).

In development:

- Ability to register single tenant apps.
- Updates to servicePrincipal.
- Migration of existing Azure AD apps to updated model.
- Support for appRoles, pre-authorized clients, optional claims, group membership claims, and branding
- Microsoft account (MSA) users can register apps.

### Azure AD v2.0 endpoint is not supported for CSP apps

Cloud solution provider (CSP) apps must acquire tokens from the Azure AD (v1) endpoints to successfully call Microsoft Graph in their partner-managed customers. Currently, acquiring a token through the newer Azure AD v2.0 endpoint is not supported.

### Pre-consent for CSP apps doesn't work in some customer tenants

Under certain circumstances, pre-consent for cloud solution provider (CSP) apps might not work for some of your customer tenants.

- For apps using delegated permissions, when using the app for the first time with a new customer tenant, you might receive this error after sign-in: `AADSTS50000: There was an error issuing a token`.
- For apps using application permissions, your app can acquire a token, but unexpectedly gets an access denied message when calling Microsoft Graph.

We are working to fix this issue as soon as possible, so that pre-consent will work for all your customer tenants.

In the meantime, to unblock development and testing, you can use the following workaround.

> [!NOTE]
> This is not a permanent solution and is only intended to unblock development. This workaround will not be required after the issue is fixed. This workaround does not need to be undone after the fix is in place.

1. Open an Azure AD v2 PowerShell session and connect to your `customer` tenant by entering your admin credentials into the sign-in window. You can download and install Azure AD PowerShell V2 from [here](https://www.powershellgallery.com/packages/AzureAD).

    ```PowerShell
    Connect-AzureAd -TenantId {customerTenantIdOrDomainName}
    ```

2. Create the Microsoft Graph service principal.

    ```PowerShell
    New-AzureADServicePrincipal -AppId 00000003-0000-0000-c000-000000000000
    ```


## Calendar

### Error accessing a shared calendar

When attempting to access events in a calendar that has been shared by another user using the following operation:

```http
GET /users/{id}/calendars/{id}/events
```

You may get HTTP 500 with the error code `ErrorInternalServerTransientError`. The error occurs because:

- Historically, there are two ways that calendar sharing has been implemented, which, for the purpose of differentiating them,
are referred to as the "old" approach and "new" approach.
- The new approach is currently available for sharing calendars with view or edit permissions, but not with delegate permissions.
- You can use the calendar REST API to view or edit shared calendars only if the calendars were shared using the **new** approach.
- You cannot use the calendar REST API to view or edit such calendars (or their events) if the calendars were shared using the **old** approach.

If a calendar was shared with view or edit permissions but using the old approach, you can now work around the error and manually upgrade the calendar sharing to use the new approach.
Over time, Outlook will automatically upgrade all shared calendars to use the new approach, including calendars shared with delegate permissions.

To manually upgrade a shared calendar to use the new approach, follow these steps:

1. The recipient removes the calendar that was previously shared to them.
2. The calendar owner re-shares the calendar in Outlook on the web, Outlook on iOS, or Outlook on Android.
3. The recipient re-accepts the shared calendar using Outlook on the web. (It will be possible to use other Outlook clients soon.)
4. The recipient verifies that the calendar has been re-shared successfully using the new approach by being able to view the shared calendar in Outlook on iOS or Outlook on Android.

A calendar shared with you in the new approach appears as just another calendar in your mailbox. You can use the calendar REST API to view or edit
events in the shared calendar, as if it's your own calendar. As an example:

```http
GET /me/calendars/{id}/events
```

### Partial support for adding and accessing ICS-based calendars in user's mailbox

Currently, calendars based on an Internet Calendar Subscription (ICS) are only partially supported:

- You can add an ICS-based calendar to a user mailbox through the UI, but not through the Microsoft Graph API.
- [Listing the user's calendars](/graph/api/user-list-calendars) lets you get the **name**, **color** and **id** properties of each [calendar](/graph/api/resources/calendar) in the user's default calendar group, or a specified calendar group, including any ICS-based calendars. You cannot store or access the ICS URL in the calendar resource.
- You can also [list the events](/graph/api/calendar-list-events) of an ICS-based calendar.

### Error attaching large files to events

An app with delegated permissions returns `HTTP 403 Forbidden` when attempting to [attach large files](outlook-large-attachments.md) to an Outlook message or event that is in a shared or delegated mailbox. With delegated permissions, [createUploadSession](/graph/api/attachment-createuploadsession) succeeds only if the message or event is in the signed-in user's mailbox.

### onlineMeetingUrl property is not supported for Microsoft Teams

Currently, the **onlineMeetingUrl** property of a Skype meeting [event](/graph/api/resources/event) would indicate the online meeting URL. However, that property for a Microsoft Teams meeting event is set to null.

The beta version offers a workaround, where you can use the **onlineMeetingProvider** property of an [event](/graph/api/resources/event?view=graph-rest-beta&preserve-view=true) to verify that the provider is Microsoft Teams. Through the **onlineMeeting** property of the **event**, you can access the **joinUrl**.

## Change notifications

### Update notifications occur on creation and soft deletion of users

[Subscriptions](/graph/api/resources/subscription) to changes for **user** with **changeType** set to **updated** will also receive notifications of **changeType**: **updated** on user creation and user soft deletion.

### Update notifications occur on creation and soft deletion of groups

[Subscriptions](/graph/api/resources/subscription) to changes for **group** with **changeType** set to **updated** will also receive notifications of **changeType**: **updated** on group creation and group soft deletion.

## Contacts

### GET operation does not return default contacts folder

In the `/v1.0` version, `GET /me/contactFolders` does not include the user's default contacts folder.

A fix will be made available. Meanwhile, you can use the following [list contacts](/graph/api/user-list-contacts) query and the **parentFolderId** property
as a workaround to get the folder ID of the default contacts folder:

```http
GET https://graph.microsoft.com/v1.0/me/contacts?$top=1&$select=parentFolderId
```

In this request:

1. `/me/contacts?$top=1` gets the properties of a [contact](/graph/api/resources/contact) in the default contacts folder.
2. Appending `&$select=parentFolderId` returns only the contact's **parentFolderId** property, which is the ID of the default contacts folder.


### Accessing contacts via a contact folder doesn't work in beta

In the `/beta` version, an issue currently prevents accessing a [contact](/graph/api/resources/contact?view=graph-rest-beta&preserve-view=true)
by specifying its parent folder in the REST request URL, as shown in the following two scenarios.

Accessing a contact from a user's top-level [contactFolder](/graph/api/resources/contactfolder?view=graph-rest-beta&preserve-view=true):

```http
GET /me/contactfolders/{id}/contacts/{id}
GET /users/{id | userPrincipalName}/contactfolders/{id}/contacts/{id}
```

Accessing a contact contained in a child folder of a **contactFolder**: 

```http
GET /me/contactFolders/{id}/childFolders/{id}/.../contacts/{id}
GET /users/{id | userPrincipalName}/contactFolders/{id}/childFolders/{id}/contacts/{id}
```

The previous example shows one level of nesting, but a contact can be located in a child of a child and so on.

As an alternative, you can simply [get](/graph/api/contact-get?view=graph-rest-beta&preserve-view=true) the contact by specifying its ID as shown,
because GET /contacts in the `/beta` version applies to all the contacts in the user's mailbox:

```http
GET /me/contacts/{id}
GET /users/{id | userPrincipalName}/contacts/{id}
```

## Customer booking

### Error when querying bookingBusinesses

Getting the list of `bookingBusinesses` fails with the following error code when an organization has several Bookings businesses and the account making the request is not an administrator:

```json
{
  "error": {
    "code": "ErrorExceededFindCountLimit",
    "message":
      "The GetBookingMailboxes request returned too many results. Please specify a query to limit the results.",
  }
}
```

As a workaround, you can limit the set of businesses returned by the request by including a `query` parameter, for example:

```http
GET https://graph.microsoft.com/beta/bookingBusinesses?query=Fabrikam
```

## Delta query

### OData context is returned incorrectly

OData context is sometimes returned incorrectly when tracking changes to relationships.

### Schema extensions are not returned with `select`

Schema extensions (legacy) are not returned with `$select` statement, but are returned without `$select`.

### Clients cannot track changes to open extensions

Clients cannot track changes to open extensions or registered schema extensions.

## Devices and apps | Device updates (Windows updates)

### Accessing and updating deployment audiences is not supported

Accessing and updating deployment audiences on **deployment** resources created via Intune is not currently supported.

- [Listing deployment audience members](/graph/api/windowsupdates-deploymentaudience-list-members) and [listing deployment audience exclusions](/graph/api/windowsupdates-deploymentaudience-list-exclusions) returns `404 Not Found`.
- [Updating deployment audience members and exclusions](/graph/api/windowsupdates-deploymentaudience-updateaudience) or [updating by ID](/graph/api/windowsupdates-deploymentaudience-updateaudiencebyid) returns `202 Accepted` but the audience is not updated.

## Extensions

### Change tracking is not supported

Change tracking (delta query) is not supported for open or schema extension properties.

### Unable to create a resource and open extension at the same time

You cannot specify an open extension at the same time you create an instance of **administrativeUnit**, **device**, **group**, **organization** or **user**. You must first create the instance and then specify the open extension data in a subsequent ``POST`` request on that instance.

### Unable to create a resource instance and add schema extension data at the same time

You cannot specify a schema extension in the same operation as creating an instance of **contact**, **event**, **message**, or **post**.
You must first create the resource instance and then do a `PATCH` to that instance to add a schema extension and custom data.

### Limit of 100 schema extension property values allowed per resource instance

Directory resources, such as **device**, **group**, and **user**, currently limit the total number of schema extension property values that can be set on a resource instance to 100.

### Owner must be specified when updating a schemaExtension definition using Microsoft Graph Explorer

When using `PATCH` to update a schemaExtension using Graph Explorer, you must specify the **owner** property and set it to its current `appId` value (which will need to be an `appId` of an application that you own). This is also the case for any client application the `appId` for which is not the same as the **owner**.

### Filtering on schema extension properties is not supported on all entity types

Filtering on schema extension properties (using the `$filter` expression) is not supported for Outlook entity types - **contact**, **event**, **message**, or **post**.

## Files (OneDrive)

### Accessing a user's drive before user accesses it leads to error

First-time access to a user's personal drive through Microsoft Graph before the user accesses their personal site through a browser leads to a `401` response.

## Groups

### Admins must consent to permissions for groups and Microsoft Teams

Microsoft Graph exposes two permissions ([*Group.Read.All*](permissions-reference.md#group-permissions) and [*Group.ReadWrite.All*](permissions-reference.md#group-permissions)) for access to the APIs for groups and Microsoft Teams.
These permissions must be consented to by an administrator.
In the future, we plan to add new permissions for groups and Teams that users can consent to.

### Some group APIs don't support delegated or app-only permissions

Only the API for core group administration and management supports access using delegated or app-only permissions. 
All other features of the group API support only delegated permissions.

Examples of group features that support delegated and app-only permissions:

- Creating and deleting groups
- Getting and updating group properties pertaining to group administration or management
- Group [directory settings](/graph/api/resources/directoryobject), type, and synchronization
- Group owners and membership
- Getting group conversations and threads

Examples of group features that support only delegated permissions:

- Group events, photo
- External senders, accepted or rejected senders, group subscription
- User favorites and unseen count

### Microsoft Graph bypasses group policies configured through Outlook on the web

Using Microsoft Graph to create and name a Microsoft 365 group bypasses any Microsoft 365 group policies that are configured through Outlook on the web.

### allowExternalSenders property can only be accessed on unified groups

There is currently an issue that prevents setting the **allowExternalSenders** property of a group in a POST or PATCH operation, in both `/v1.0` and `/beta`.

The **allowExternalSenders** property can only be accessed on unified groups. Accessing this property on security groups, including via GET operations, will result in an error.

### Removing a group owner also removes the user as a group member

When [DELETE /groups/{id}/owners](/graph/api/group-delete-owners) is called for a group that is associated with a [team](/graph/api/resources/team), the user is also removed from the /groups/{id}/members list. To work around this, remove the user from both owners and members, then wait 10 seconds, then add them back to members.

## Identity and access

### Conditional access policy requires consent to permission

The [conditionalAccessPolicy](/graph/api/resources/conditionalaccesspolicy) API currently requires consent to the **Policy.Read.All** permission to call the POST and PATCH methods. In the future, the **Policy.ReadWrite.ConditionalAccess** permission will enable you to read policies from the directory.

### Claims mapping policy might require consent to permissions

The [claimsMappingPolicy](/graph/api/resources/claimsmappingpolicy) API might require consent to both the **Policy.Read.All** and **Policy.ReadWrite.ConditionalAccess** permissions for the `LIST /policies/claimsMappingPolicies` and `GET /policies/claimsMappingPolicies/{id}` methods, as follows:

+ If no **claimsMappingPolicy** objects are available to retrieve in a LIST operation, either permission is sufficient to call this method.
+ If there are **claimsMappingPolicy** objects to retrieve, your app must consent to both permissions. If not, a `403 Forbidden` error is returned.

In the future, either permission will be sufficient to call both methods.

### Non-Windows devices can't be updated by an app with application permissions

When an app with application permissions attempts to update any properties of the device object where the **operationSystem** property isn't `Windows`, apart from the **extensionAttributes** property, the [Update device](/graph/api/device-update) API returns a `400 Bad request` error code with the error message "Properties other than ExtendedAttribute1..15 can be modified only on windows devices.". Use delegated permissions to update the properties of non-Windows devices.

## JSON batching

### Nested batches are not supported

JSON batch requests must not contain any nested batch requests.

### All individual requests must be synchronous

All requests contained in a batch request must be run synchronously. If present, the `respond-async` preference will be ignored.

### Transactional processing of requests is not supported

Microsoft Graph does not currently support transactional processing of individual requests. The **atomicityGroup** property on individual requests will be ignored.

### URIs must be relative

Always specify relative URIs in batch requests. Microsoft Graph then makes these URLs absolute by using the version endpoint included in the batch URL.

### Batch size is limited

JSON batch requests are currently limited to 20 individual requests. 

- Depending on the APIs part of the batch request, the underlying services impose their own throttling limits that affect applications that use Microsoft Graph to access them.
- Requests in a batch are evaluated individually against throttling limits and if any request exceeds the limits, it fails with a status of 429.

For more details, visit [Throttling and batching](/graph/throttling#throttling-and-batching).

### Request dependencies are limited

Individual requests can depend on other individual requests. Currently, requests can only depend on a single other request, and must follow one of these three patterns:

- Parallel - no individual request states a dependency in the **dependsOn** property.
- Serial - all individual requests depend on the previous individual request.
- Same - all individual requests that state a dependency in the **dependsOn** property state the same dependency. **Note**: Requests made using this pattern will run sequentially.

As JSON batching matures, these limitations will be removed.

## Mail (Outlook)

### Attaching large files to messages with delegated permissions can fail
An app with delegated permissions returns `HTTP 403 Forbidden` when attempting to [attach large files](outlook-large-attachments.md) to an Outlook message or event that is in a shared or delegated mailbox. With delegated permissions, [createUploadSession](/graph/api/attachment-createuploadsession) succeeds only if the message or event is in the signed-in user's mailbox.

### The comment parameter for creating a draft does not become part of the message body

The **comment** parameter for creating a reply or forward draft ([createReply](/graph/api/message-createreply),
[createReplyAll](/graph/api/message-createreplyall), [createForward](/graph/api/message-createforward))
does not become part of the body of the resultant message draft.

### GET messages returns chats in Microsoft Teams

In both the v1.0 and beta endpoints, the response to `GET /users/id/messages` includes the user's Microsoft Teams chats that occurred outside the scope of a team or channel. These chat messages have "IM" as their subject.

## Query parameters 

### Some limitations apply to query parameters

The following limitations apply to query parameters:

- Multiple namespaces are not supported.
- GET requests on `$ref` with casting are not supported on users, groups, devices, service principals, and applications.
- `@odata.bind` is not supported. This means that you can't properly set the **acceptedSenders** or **rejectedSenders** navigation property on a group.
- `@odata.id` is not present on non-containment navigations (like messages) when using minimal metadata.
- `$expand`:
  - For directory objects, returns a maximum of 20 objects.
  - No support for `@odata.nextLink`.
  - No support for more than one level of expand.
  - For directory objects, no support for nesting other query parameters such as `$filter` and `$select` in `$expand`.
- `$filter`
  - `/attachments` endpoint does not support filters. If present, the `$filter` parameter is ignored.
  - Cross-workload filtering is not supported.
- `$search`:
  - Full-text search is only available for a subset of entities, such as messages.
  - Cross-workload searching is not supported.
  - Searching is not supported in Azure AD B2C tenants.
- `$count`:
  - Not supported in Azure AD B2C tenants.
  - When using the `$count=true` query string when querying against directory objects, the `@odata.count` property will be present only in the first page of the paged data.
- Query parameters specified in a request might fail silently. This can be true for unsupported query parameters as well as for unsupported combinations of query parameters.

## Sites and lists (SharePoint)

### Follow/unfollow sites is not in sync with SharePoint following

When querying [followed sites](/graph/api/sites-list-followed) through Microsoft Graph, the response might have incorrect results and those results might not match the results from following content in SharePoint. As a temporary workaround, you can use the [Following people and content REST API](/sharepoint/dev/general-development/following-people-and-content-rest-api-reference-for-sharepoint).

## Teamwork and communications (Microsoft Teams)

### Unable to filter team members by roles

Role query filters along with other filters `GET /teams/team-id/members?$filter=roles/any(r:r eq 'owner') and displayName eq 'dummy'` might not work. The server might respond with a `BAD REQUEST`.

### Requests to filter team members by role require a parameter

All the requests to filter team members by roles expect either a _skipToken_ parameter or a _top_ paramater in the request, but not both. If both the parameters are passed in the request, the _top_ parameter will be ignored.

### Some properties for chat members might be missing in the response to a GET request

In certain instances, the `tenantId` / `email` / `displayName` property for the individual members of a chat might not be populated on a `GET /chats/chat-id/members` or `GET /chats/chat-id/members/membership-id` request.

### Properties are missing in the list of teams that a user has joined

The API call for [me/joinedTeams](/graph/api/user-list-joinedteams) returns only the **id**, **displayName**, and **description** properties of a [team](/graph/api/resources/team). To get all properties, use the [Get team](/graph/api/team-get) operation.

### Installation of apps that require resource-specific consent permissions is not supported

The following API calls do not support installing apps that require [resource-specific consent](/microsoftteams/platform/graph-api/rsc/resource-specific-consent) permissions.

- [Add app to team](/graph/api/team-post-installedapps)
- [Upgrade app installed in team](/graph/api/team-teamsappinstallation-upgrade)
- [Add app to chat](/graph/api/chat-post-installedapps)
- [Upgrade app installed in chat](/graph/api/chat-teamsappinstallation-upgrade)

### Unable to access a cross-tenant shared channel when the request URL contains tenants/{cross-tenant-id}

The API calls for [teams/{team-id}/incomingChannels](/graph/api/team-list-incomingchannels) and [teams/{team-id}/allChannels](/graph/api/team-list-allchannels) return the **@odata.id** property which you can use to access the channel and run other operations on the [channel](/graph/api/resources/channel) object. If you call the URL returned from the **@odata.id** property, the request fails with the following error when it tries to access the cross-tenant shared [channel](/graph/api/resources/channel):
```http
GET /tenants/{tenant-id}/teams/{team-id}/channels/{channel-id}
{
    "error": {
        "code": "BadRequest",
        "message": "TenantId in the optional tenants/{tenantId} segment should match the tenantId(tid) in the token used to call Graph.",
        "innerError": {
            "date": "2022-03-08T07:33:50",
            "request-id": "dff19596-b5b2-421d-97d3-8d4b023263f3",
            "client-request-id": "32ee2cbd-27f8-2441-e3be-477dbe0cedfa"
        }
    }
}
```

To solve this issue, remove the `/tenants/{tenant-id}` part from the URL before you call the API to access the cross-tenant shared [channel](/graph/api/resources/channel).

### TeamworkAppSettings permissions are not visible in the Azure portal

The permissions TeamworkAppSettings.Read.All and TeamworkAppSettings.ReadWrite.All are currently being rolled out and might not be visible in Azure Portal yet. To consent to these permissions, please use an authorize request as follows:

```http
GET https://login.microsoftonline.com/{tenant-id}/oauth2/v2.0/authorize?client_id={client-app-id}&response_type=code&scope=https://graph.microsoft.com/TeamworkAppSettings.ReadWrite.All
```

### Create channel can return an error response

When you create a channel, if you use special characters in your channel name, the [Get filesFolder](/graph/api/channel-get-filesfolder) API will return a `400 Bad Request` error response. When you create a channel, make sure that the **displayName** for the channel does not:

- Include any of the following special characters: ~ # % & * { } + / \ : < > ? | ‘ ”.
- Start with an underscore (_) or period (.), or end with a period (.).

### View meeting details menu is not available on Microsoft Teams client

The Microsoft Teams client does not show the **View Meeting details**  menu for channel meetings created via the cloud communications API.

## Users

### Encode number (#) symbols in userPrincipalName

The **userPrincipalName** of guest users added through Azure AD B2B often contains the number (#) character. Using `$filter` on a **userPrincipalName** that contains the # symbol, for example, `GET /users?$filter=userPrincipalName eq 'AdeleV_contoso.com#EXT#@fabrikam.com'`, returns a `400 Bad request` HTTP error response. To filter by the **userPrincipalName**, encode the # character using its UTF-8 equivalent (`%23`), for example, `GET /users?$filter=userPrincipalName eq 'AdeleV_contoso.com%23EXT%23@fabrikam.com'`.

### Access to user resources is delayed after creation

Users can be created immediately through a POST on the user entity. A Microsoft 365 license must first be assigned to a user, in order to get access to Microsoft 365 services. Even then, due to the distributed nature of the service, it might take 15 minutes before files, messages, and events entities are available for use for this user, through the Microsoft Graph API. During this time, apps will receive a `404 Not Found` HTTP error response.

### Access to a user's profile photo is limited

1. Reading and updating a user's profile photo is only possible if the user has a mailbox. Failure to read or update a photo, in this case, results in the following error:

    ```html
    {
      "error": {
        "code": "ErrorNonExistentMailbox",
        "message": "The SMTP address has no mailbox associated with it."
      }
    }
    ```

2. Any photos that *may* have been previously stored using the **thumbnailPhoto** property (using the Azure AD Graph API (deprecated) or through AD Connect synchronization) are no longer accessible through the Microsoft Graph **photo** property of the [user](/graph/api/resources/user) resource.
3. Managing users' photos through the [profilePhoto resource](/graph/api/resources/profilephoto) of the Microsoft Graph API is currently not supported in Azure AD B2C tenants.

### Revoke sign-in sessions returns wrong HTTP code

The [user: revokeSignInSessions API](/graph/api/user-revokesigninsessions) should return a `204 No content` response for successful revocations, and an HTTP error code (4xx or 5xx) if anything goes wrong with the request.  However, due to a service issue, this API returns a `200 OK` and a Boolean parameter that is always `true`.  Until this is fixed, you can treat any 2xx return code as success for this API.

### Incomplete objects are returned when using getByIds request

Requesting objects using [Get directory objects from a list of IDs](/graph/api/directoryobject-getbyids) should return full objects. However, currently [user](/graph/api/resources/user) objects on the v1.0 endpoint are returned with a limited set of properties. As a temporary workaround, when you use the operation in combination with the `$select` query option, more complete [user](/graph/api/resources/user) objects will be returned. This behavior is not in accordance with the OData specifications. Because this behavior might be updated in the future, use this workaround only when you provide `$select=` with all the properties you are interested in, and only if future breaking changes to this workaround are acceptable.

### showInAddressList property is out of sync with Microsoft Exchange

When querying users through Microsoft Graph, the **showInAddressList** property may not indicate the same status shown in Microsoft Exchange. We recommend you manage this functionality directly with Microsoft Exchange through the Microsoft 365 admin center and not to use this property in Microsoft Graph.

## Functionality available only in Office 365 REST or Azure AD Graph APIs (deprecated)

Some functionality is not yet available in Microsoft Graph. If you don't see the functionality you're looking for, you can use the endpoint-specific [Office 365 REST APIs](/previous-versions/office/office-365-api/). For Azure AD Graph, see [Migrate Azure Active Directory (Azure AD) Graph apps to Microsoft Graph](./migrate-azure-ad-graph-overview.md).
