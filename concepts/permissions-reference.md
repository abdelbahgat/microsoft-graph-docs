---
title: "Microsoft Graph permissions reference "
description: "Microsoft Graph exposes granular permissions that control the access that apps have to resources, like users, groups, and mail. As a developer, you decide which permissions for Microsoft Graph your app requests."
author: "FaithOmbongi"
ms.author: ombongifaith
ms.reviewer: jackson.woods
ms.localizationpriority: high
ms.topic: reference
ms.prod: "applications"
ms.custom: graphiamtop20, scenarios:getting-started
ms.date: 04/12/2023
---

# Microsoft Graph permissions reference

For an app to access data in Microsoft Graph, the user or administrator must grant it the permissions it needs. This topic lists the delegated and application permissions exposed by Microsoft Graph. For guidance about how to use the permissions, see the [Overview of Microsoft Graph permissions](permissions-overview.md).

To find the unique identifiers for all permissions, see [All permissions and IDs](#all-permissions-and-ids).

[!INCLUDE [auth-use-least-privileged](../includes/auth-use-least-privileged.md)]

## Access reviews permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _AccessReview.Read.All_ |   Read all access reviews  | Allows the app to read access reviews on behalf of the signed-in user. | Yes | No |
| _AccessReview.ReadWrite.All_ |   Manage all access reviews  | Allows the app to read and write access reviews on behalf of the signed-in user. | Yes | No |
| _AccessReview.ReadWrite.Membership_ |   Manage access reviews for group and app memberships | Allows the app to read and write access reviews of groups and apps on behalf of the signed-in user. | Yes | No |



#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _AccessReview.Read.All_ |   Read all access reviews | Allows the app to read access reviews without a signed-in user. | Yes |
| _AccessReview.ReadWrite.All_ |   Manage all access reviews | Allows the app to read, update, delete and perform actions on access reviews, reviewers, decisions and settings in the organization, without a signed-in user. | Yes |
| _AccessReview.ReadWrite.Membership_ | Manage access reviews for group and app memberships | Allows the app to manage access reviews of groups and apps without a signed-in user. | Yes |


### Remarks

_AccessReview.Read.All_, _AccessReview.ReadWrite.All_, _AccessReview.ReadWrite.Membership_ are valid only for work or school accounts.

For an app with delegated permissions to read access reviews of a group or app, the signed-in user must be a member of one of the following administrator roles: Global Administrator, Security Administrator, Security Reader or User Administrator. For an app with delegated permissions to write access reviews of a group or app, the signed-in user must be a member of one of the following administrator roles: Global Administrator or User Administrator.

For an app with delegated permissions to read access reviews of an Azure AD role, the signed-in user must be a member of one of the following administrator roles: Global Administrator, Security Administrator, Security Reader or Privileged Role Administrator. For an app with delegated permissions to write access reviews of an Azure AD role, the signed-in user must be a member of one of the following administrator roles: Global Administrator or Privileged Role Administrator.

For more information about administrator roles, see [Assigning administrator roles in Azure Active Directory](/azure/active-directory/active-directory-assign-admin-roles).

---

## Administrative units permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _AdministrativeUnit.Read.All_ |   Read administrative units  | Allows the app to read administrative units and administrative unit membership on behalf of the signed-in user. | Yes | No |
| _AdministrativeUnit.ReadWrite.All_ |   Read and write administrative units  | Allows the app to create, read, update, and delete administrative units and manage administrative unit membership on behalf of the signed-in user. | Yes | No |


#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _AdministrativeUnit.Read.All_ |   Read all administrative units | Allows the app to read administrative units and administrative unit membership without a signed-in user. | Yes |
| _AdministrativeUnit.ReadWrite.All_ |   Read and write all administrative units | Allows the app to create, read, update, and delete administrative units and manage administrative unit membership without a signed-in user. | Yes |

### Remarks
With the _AdministrativeUnit.Read.All_ permission an application can read administrative unit information including members.

With the _AdministrativeUnit.ReadWrite.All_ permission an application can create, read, update, and delete administrative unit information including members.

_AdministrativeUnit.Read.All_ and _AdministrativeUnit.ReadWrite.All_ are valid only for work or school accounts.

### Example usage

> [!NOTE]
> The `v1.0` endpoint for the administrative units API is `/v1.0/directory/administrativeUnits`.

- _AdministrativeUnit.Read.All_: Read administrative units (`GET /beta/administrativeUnits`)
- _AdministrativeUnit.Read.All_: Read members list of an administrative unit (`GET /beta/administrativeUnits/<id>/members`)
- _AdministrativeUnit.ReadWrite.All_: Create an administrative unit (`POST /beta/administrativeUnits`)
- _AdministrativeUnit.ReadWrite.All_: Update an administrative unit (`PATCH /beta/administrativeUnits/<id>`)
- _AdministrativeUnit.ReadWrite.All_: Add members to an administrative unit  (`POST /beta/administrativeUnits/<id>/members`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Analytics resource permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Analytics.Read_ |   Read user activity statistics. | Allows the app to read the signed-in user's activity statistics, such as how much time the user has spent on emails, in meetings, or in chat sessions. | No |

#### Application permissions

None.

### Example usage

#### Delegated

* _Analytics.Read_: [List related settings for a user](/graph/api/useranalytics-get-settings?view=graph-rest-beta&preserve-view=true) (`GET /beta/me/analytics/settings`)

#### Application

None.

---

## AppCatalog resource permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------| :----------|
| _AppCatalog.Read.All_ | Read all app catalogs | Allows the app to read the apps in the app catalogs.| No | No |
| _AppCatalog.ReadWrite.All_ | Read and write to all app catalogs  | Allows the app to create, read, update, and delete apps in the app catalogs. | Yes | No |
|_AppCatalog.Submit_|Submit an app for admin review|Allows the user to submit and app for admin review for publication in an organization's app catalog and allows user to cancel past submissions that have not been published.</br> &#119821;&#119822;&#119827;&#119812;: Non-admin users submit apps for review by including the  `requiresReview=true` query parameter.|Yes|No|

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _AppCatalog.Read.All_ | Read all app catalogs | Allows the app to read apps in the app catalogs without a signed-in user. | Yes |
| _AppCatalog.ReadWrite.All_ | Read and write to all app catalogs | Allows the app to create, read, update, and delete apps in the app catalogs without a signed-in user. | Yes |

### Remarks

Currently the only catalog is the list of applications in [Microsoft Teams](teams-concept-overview.md).

### Example usage

#### Delegated
* _AppCatalog.ReadWrite.All_: [List all applications in catalog](/graph/api/appcatalogs-list-teamsapps) (`GET /beta/appCatalogs/teamsApps`)
* _AppCatalog.ReadWrite.All_: [Publish an app](/graph/api/teamsapp-publish?view=graph-rest-beta&preserve-view=true) (`POST /beta/appCatalogs/teamsApps`)
* _AppCatalog.ReadWrite.All_: [Update a published app](/graph/api/teamsapp-update?view=graph-rest-beta&preserve-view=true) (`PATCH /beta/appCatalogs/teamsApps/{id}`)
* _AppCatalog.ReadWrite.All_: [Remove a published app](/graph/api/teamsapp-delete?view=graph-rest-beta&preserve-view=true) (`DELETE /beta/appCatalogs/teamsApps/{id}`)

#### Application

None.

---

## Application resource permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Application.Read.All_ | Read applications | Allows the app to read applications and service principals on behalf of the signed-in user. | Yes |
| _Application.ReadWrite.All_ | Read and write all apps |  Allows the app to create, read, update and delete applications and service principals on behalf of the signed-in user. | Yes |
| _AppRoleAssignment.ReadWrite.All_ | Manage app permission grants and app role assignments | Allows the app to manage permission grants for application permissions to any API (including Microsoft Graph) and application assignments for any app, on behalf of the signed-in user. | Yes |
| _DelegatedPermissionGrant.ReadWrite.All_ | Manage delegated permission grants | Allows the app to manage delegated permission grants for any API (including Microsoft Graph), on behalf of the signed-in user. | Yes |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Application.Read.All_ | Read applications | Allows the app to read applications and service principals without a signed-in user. | Yes |
| _Application.ReadWrite.All_ | Read and write all apps | Allows the calling app to create, and manage (read, update, update application secrets and delete) applications and service principals without a signed-in user.  Does not allow management of consent grants or application assignments to users or groups. | Yes |
| _Application.ReadWrite.OwnedBy_ | Manage apps that this app creates or owns | Allows the calling app to create other applications and service principals, and fully manage those applications and service principals (read, update, update application secrets and delete), without a signed-in user.  It cannot update any applications that it is not an owner of. Does not allow management of consent grants or application assignments to users or groups. | Yes |
| _AppRoleAssignment.ReadWrite.All_ | Manage app permission grants and app role assignments | Allows the app to manage permission grants for application permissions to any API (including Microsoft Graph) and application assignments for any app, without a signed-in user. | Yes |
| _DelegatedPermissionGrant.ReadWrite.All_ | Manage all delegated permission grants | Allows the app to grant or revoke any delegated permission for any API (including Microsoft Graph), without a signed-in user. | Yes |

### Remarks

> [!CAUTION]
> Permissions that allow granting authorization, such as _AppRoleAssignment.ReadWrite.All_, allow an application to grant additional privileges to itself, other applications, or any user. Likewise, permissions that allow managing credentials, such as _Application.ReadWrite.All_, allow an application to act as other entities, and use the privileges they were granted. Use caution when granting any of these permissions.

The _Application.ReadWrite.OwnedBy_ permission allows the same operations as _Application.ReadWrite.All_ except that the former allows these operations only on applications and service principals that the calling app is an owner of. Ownership is indicated by the `owners` navigation property on the target [application](/graph/api/application-list-owners?view=graph-rest-beta&preserve-view=true) or [service principal](/graph/api/serviceprincipal-list-owners?view=graph-rest-beta&preserve-view=true) resource.

> [!NOTE]
> The *Application.ReadWrite.OwnedBy* permission allows an app to call `GET /applications` and `GET /servicePrincipals` to list all applications and service principals in the tenant. This scope of access has been allowed for the permission.

### Example usage

#### Delegated

* _Application.Read.All_: List all applications (`GET /v1.0/applications`)
* _Application.ReadWrite.All_: Update a service principal (`PATCH /v1.0/servicePrincipals/{id}`)

#### Application

* _Application.Read.All_: List all applications (`GET /v1.0/applications`)
* _Application.ReadWrite.All_: Delete a service principal (`DELETE /v1.0/servicePrincipals/{id}`)
* _Application.ReadWrite.OwnedBy_: Create an application (`POST /v1.0/applications`)
* _Application.ReadWrite.OwnedBy_: List all applications owned by the calling application (`GET /v1.0/servicePrincipals/{id}/ownedObjects`)
* _Application.ReadWrite.OwnedBy_: Add another owner to an owned application (`POST /v1.0/applications/{id}/owners/$ref`).
  
    > NOTE: This may require additional permissions.

---

## Audit log permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _AuditLog.Read.All_ | Read audit log data | Allows the app to read and query your audit log activities, on behalf of the signed-in user. | Yes | No |

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
|_AuditLog.Read.All_ |Read all audit log data |Allows the app to read and query your audit log activities, without a signed-in user. |Yes |

---

## BitLocker recovery key permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _BitlockerKey.ReadBasic.All_ | Read basic BitLocker key information | Allows an app to read the BitLocker key's properties for all devices in the tenant. The recovery key is not returned. | Yes | No |
| _BitlockerKey.Read.All_ | Read the BitLocker key | Allows an app to read the BitLocker keys for all devices in the tenant. The recovery key is returned. | Yes | No |

#### Application permissions

None.

### Example usage

#### Delegated

* _BitlockerKey.ReadBasic.All_: List the BitLocker recovery keys for all devices in the tenant without returning the 'key' property (`GET /bitlocker/recoveryKeys`).
* _BitlockerKey.Read.All_: Get a BitLocker recovery key with the recovery key (`GET /bitlocker/recoveryKeys/{bitlockerRecoveryKeyId}?$select=key`)

---

## Bookings permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Bookings.Read.All_ |  Allows an app to read Bookings appointments, businesses, customers, services, and staff on behalf of the signed-in user. | Intended for read-only applications. Typical target user is the customer of a booking business. | No | No |
| _BookingsAppointment.ReadWrite.All_ | Allows an app to read and write Bookings appointments and customers, and additionally allows reading businesses, services, and staff on behalf of the signed-in user. | Intended for scheduling applications which need to manipulate appointments and customers. Cannot change fundamental information about the booking business, nor its services and staff members. Typical target user is the customer of a booking business.| No | No |
| _Bookings.ReadWrite.All_ | Allows an app to read and write Bookings appointments, businesses, customers, services, and staff on behalf of the signed-in user. Does not allow create, delete, or publish of Bookings businesses. | Intended for management applications that manipulate existing businesses, their services and staff members. Cannot create, delete, or change the publishing status of a booking business. Typical target user is the support staff of an organization.| No | No |
| _Bookings.Manage.All_ | Allows an app to read, write, and manage Bookings appointments, businesses, customers, services, and staff on behalf of the signed-in user.  | Allows the app to have full access. <br>Intended for a full management experience. Typical target user is the administrator of an organization.| No | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Bookings.Read.All_ |  Allows an app to read Bookings appointments, businesses, customers, services, and staff on behalf of the signed-in user. | Intended for read-only applications. Typical target user is the customer of a booking business. | Yes | No |
| _BookingsAppointment.ReadWrite.All_ | Allows an app to read and write Bookings appointments and customers, and additionally allows reading businesses, services, and staff on behalf of the signed-in user. | Intended for scheduling applications which need to manipulate appointments and customers. Cannot change fundamental information about the booking business, nor its services and staff members. Typical target user is the customer of a booking business.| Yes | No |
| _Bookings.ReadWrite.All_ | Allows an app to read and write Bookings appointments, businesses, customers, services, and staff on behalf of the signed-in user. Does not allow create, delete, or publish of Bookings businesses. | Intended for management applications that manipulate existing businesses, their services and staff members. Cannot create, delete, or change the publishing status of a booking business. Typical target user is the support staff of an organization.| Yes | No |
| _Bookings.Manage.All_ | Allows an app to read, write, and manage Bookings appointments, businesses, customers, services, and staff on behalf of the signed-in user.  | Allows the app to have full access. <br>Intended for a full management experience. Typical target user is the administrator of an organization.| Yes | No |

### Example usage

#### Delegated

* _Bookings.Read.All_: Get the ID and names of the collection of Bookings businesses that has been created for a tenant (`GET /bookingBusinesses`).
* _BookingsAppointment.ReadWrite.All_: Create an appointment for a service at a Bookings business (`POST /bookingBusinesses/{id}/appointments`).
* _Bookings.ReadWrite.All_: Create a new service for the specified Bookings business (`POST /bookingBusinesses/{id}/services`).
* _Bookings.Manage.All_: Make the scheduling page of this business available to external customers (`POST /bookingBusinesses/{id}/publish`).

---

## Browser management permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _BrowserSiteLists.Read.All_ | Read browser site lists for your organization | Allows an app to read the browser site lists configured for your organization, on behalf of the signed-in user. | No | No |
| _BrowserSiteLists.ReadWrite.All_ | Read and write browser site lists for your organization |  Allows an app to read and write the browser site lists configured for your organization, on behalf of the signed-in user. | No | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _BrowserSiteLists.Read.All_ | Read all browser site lists for your organization | Allows an app to read all browser site lists configured for your organization, without a signed-in user. | Yes | No |
| _BrowserSiteLists.ReadWrite.All_ | Read and write all browser site lists for your organization | Allows an app to read and write all browser site lists configured for your organization, without a signed-in user. | Yes | No |

### Example usage

#### Delegated

* _BrowserSiteLists.Read.All_: List all browser site lists, on behalf of a signed-in user (`GET /beta/admin/edge/internetExplorerMode/siteLists`)
* _BrowserSiteLists.ReadWrite.All_: Update a browser site list, on behalf of a signed-in user (`PATCH /beta/admin/edge/internetExplorerMode/siteLists/{browserSiteListId}`)

#### Application

* _BrowserSiteLists.Read.All_: List all browser site lists, without a signed-in user (`GET /beta/admin/edge/internetExplorerMode/siteLists`)
* _BrowserSiteLists.ReadWrite.All_: Delete a browser site list, without a signed-in user (`DELETE /beta/admin/edge/internetExplorerMode/siteLists/{browserSiteListId}`)

---

## Business scenarios permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|BusinessScenarioConfig.Read.All|Read business scenario configurations|Allows the app to read the configurations for the business scenarios of your organization, on behalf of the signed-in user.|Yes|No|
|BusinessScenarioConfig.Read.OwnedBy|Read business scenario configurations this app creates or owns|Allows the app to read the configurations of business scenarios it owns, on behalf of the signed-in user.|Yes|No|
|BusinessScenarioConfig.ReadWrite.All|Read and write business scenario configurations|Allows the app to read and write the configurations for the business scenarios of your organization, on behalf of the signed-in user.|Yes|No|
|BusinessScenarioConfig.ReadWrite.OwnedBy|Read and write business scenario configurations this app creates or owns|Allows the app to create new business scenarios and fully manage the configurations of scenarios it owns, on behalf of the signed-in user.|Yes|No|
|BusinessScenarioData.Read.OwnedBy|Read all data for business scenarios this app creates or owns|Allows the app to read all data associated with the business scenarios it owns. Data access will be attributed to the signed-in user.|Yes|No|
|BusinessScenarioData.ReadWrite.OwnedBy|Read and write all data for business scenarios this app creates or owns|Allows the app to fully manage all data associated with the business scenarios it owns. Data access and changes will be attributed to the signed-in user.|Yes|No|

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
|BusinessScenarioConfig.Read.OwnedBy|Read all business scenario configurations this app creates or owns|Allows the app to read the configurations of business scenarios it owns, without a signed-in user.|Yes|
|BusinessScenarioConfig.ReadWrite.OwnedBy|Read and write all business scenario configurations this app creates or owns|Allows the app to create new business scenarios and fully manage the configurations of scenarios it owns, without a signed-in user.|Yes|
|BusinessScenarioData.Read.OwnedBy|Read data for all business scenarios this app creates or owns|Allows the app to read the data associated with the business scenarios it owns, without a signed-in user.|Yes|
|BusinessScenarioData.ReadWrite.OwnedBy|Read and write data for all business scenarios this app creates or owns|Allows the app to fully manage the data associated with the business scenarios it owns, without a signed-in user.|Yes|

### Example usage

#### Delegated

* _BusinessScenarioConfig.ReadWrite.OwnedBy_: Create a new business scenario (`POST /solutions/businessScenarios`)
* _BusinessScenarioConfig.Read.All_: Get a list of all business scenarios in an organization (`GET /solutions/businessScenarios`)

#### Application

* _BusinessScenarioConfig.ReadWrite.OwnedBy_: Update the Planner plan configuration for a business scenario (`PATCH /solutions/businessScenarios/c5d514e6c6864911ac46c720affb6e4d/planner/planConfiguration`)
* _BusinessScenarioData.ReadWrite.OwnedBy_: Delete a Planner task in a business scenario (`DELETE /solutions/businessScenarios/c5d514e6c6864911ac46c720affb6e4d/planner/tasks/M60dlXLEkk-ZocLUTDvBSpcAGRaa`)

---

## Calendars permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Calendars.Read_ |Read user calendars |Allows the app to read events in user calendars. |No | Yes |
| _Calendars.Read.Shared_ |Read user and shared calendars |Allows the app to read events in all calendars that the user can access, including delegate and shared calendars. |No | No |
| _Calendars.ReadWrite_ |Have full access to user calendars |Allows the app to create, read, update, and delete events in user calendars. |No | Yes |
| _Calendars.ReadWrite.Shared_ |Read and write user and shared calendars |Allows the app to create, read, update and delete events in all calendars the user has permissions to access. This includes delegate and shared calendars.|No | No |
| _Calendars.ReadBasic_ |Read basic details of user calendars |Allows the app to read events in user calendars, except for properties such as body, attachments, and extensions.|Yes | No |

<br/>

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
|_Calendars.Read_ |Read calendars in all mailboxes |Allows the app to read events of all calendars without a signed-in user. |Yes |
|_Calendars.ReadWrite_ |Read and write calendars in all mailboxes |Allows the app to create, read, update, and delete events of all calendars without a signed-in user. |Yes |
| _Calendars.ReadBasic.All_ |Read basic details of calendars in all mailboxes|Allows the app to read events of all calendars, except for properties such as body, attachments, and extensions, without a signed-in user. |Yes |

> **Important**
Administrators can configure [application access policy](auth-limit-mailbox-access.md) to limit app access to _specific_ mailboxes and not to all the mailboxes in the organization, even if the app has been granted the application permissions of Calendars.Read or Calendars.ReadWrite.
<br/>

### Example usage

#### Delegated

* _Calendars.Read_: Get events on the user's calendar between April 23, 2017 and April 29, 2017 (`GET /me/calendarView?startDateTime=2017-04-23T00:00:00&endDateTime=2017-04-29T00:00:00`).
* _Calendars.Read.Shared_: Find meeting times where all attendees are available (`POST /users/{id|userPrincipalName}/findMeetingTimes`).
* _Calendars.ReadWrite_: Add an event to the user's calendar (`POST /me/events`).

#### Application

* _Calendars.Read_: Find events in a conference room's calendar organized by bob@contoso.com (`GET /users/{id | userPrincipalName}/events?$filter=organizer/emailAddress/address eq 'bob@contoso.com'`).
* _Calendars.Read_: List all events on a user's calendar for the month of May (`GET /users/{id | userPrincipalName}/calendarView?startDateTime=2017-05-01T00:00:00&endDateTime=2017-06-01T00:00:00`)
* _Calendars.ReadWrite_: Add an event to a user's calendar for approved time off  (`POST /users/{id | userPrincipalName}/events`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

## Calls permissions

#### Delegated permissions

None.

<br/>

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
|_Calls.Initiate.All_|Initiate outgoing 1:1 calls from the app|Allows the app to place outbound calls to a single user and transfer calls to users in your organization's directory, without a signed-in user.|Yes|
|_Calls.InitiateGroupCall.All_|Initiate outgoing group calls from the app|Allows the app to place outbound calls to multiple users and add participants to meetings in your organization, without a signed-in user.|Yes|
|_Calls.JoinGroupCall.All_|Join group calls and meetings as an app|Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user. The app will be joined with the privileges of a directory user to meetings in your tenant.|Yes|
|_Calls.JoinGroupCallasGuest.All_|Join group calls and meetings as a guest|Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user. The app will be joined as a guest to meetings in your tenant.|Yes|
|_Calls.AccessMedia.All_\*|Access media streams in a call as an app|Allows the app to get direct access to media streams in a call, without a signed-in user.|Yes|

> \***Important:** You may NOT use the Cloud Communications APIs to record or otherwise persist media content from calls or meetings that your application accesses, or data derived from that media content. Make sure that you are compliant with the laws and regulations in your area regarding data protection and confidentiality of communications. Please see the [Terms of Use](/legal/microsoft-apis/terms-of-use) and consult with your legal counsel for more information.

<br/>

### Example usage

#### Application

* _Calls.Initiate.All_: Make a peer-to-peer call from the application to a user in the organization (`POST /beta/communications/calls`).
* _Calls.InitiateGroupCall.All_: Make a group call from the application to a group of users in the organization (`POST /beta/communications/calls`).
* _Calls.JoinGroupCall.All_: Join a group call or online meeting from the application (`POST /beta/communications/calls`).
* _Calls.JoinGroupCallasGuest.All_: Join a group call or online meeting from the application, but the application only has guest privileges in the meeting (`POST /beta/communications/calls`).
* _Calls.AccessMedia.All_: Create or join a call and the app gets direct access to participant media streams in the call (`POST /beta/communications/calls`).

> **Note:** For request examples, see [Create call](/graph/api/application-post-calls?view=graph-rest-beta&preserve-view=true).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

## Call records permissions

#### Delegated permissions

None.

<br/>

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
|_CallRecords.Read.All_|Read all call records|Allows the app to read call records for all calls and online meetings without a signed-in user.|Yes|
|_CallRecord-PstnCalls.Read.All_|Read PSTN and direct routing call log data|Allows the app to read all PSTN and direct routing call log data without a signed-in user.|Yes|

### Remarks

The _CallRecords.Read.All_ permission grants an application privileged access to [callRecords](/graph/api/resources/callrecords-callrecord) for every call and online meeting within your organization, including calls to and from external phone numbers. This includes potentially sensitive details about who participated in the call, as well as technical information pertaining to these calls and meetings that can be used for network troubleshooting, such as IP addresses, device details, and other network information.

The _CallRecord-PstnCalls.Read.All_ permission grants an application access to [PSTN (calling plans)](/graph/api/callrecords-callrecord-getpstncalls) and [direct routing](/graph/api/callrecords-callrecord-getdirectroutingcalls) call logs. This includes potentially sensitive information about users as well as calls to and from external phone numbers.

> **Important:** Discretion should be used when granting these permissions to applications. Call records can provide insights into the operation of your business, and so can be a target for malicious actors. Only grant these permissions to applications you trust to meet your data protection requirements.

> **Important:** Make sure that you are compliant with the laws and regulations in your area regarding data protection and confidentiality of communications. Please see the [Terms of Use](/legal/microsoft-apis/terms-of-use) and consult with your legal counsel for more information.

<br/>

### Example usage

#### Application

* _CallRecords.Read.All_: Retrieve a call record (`GET /v1.0/communications/callRecords/{id}`).
* _CallRecords.Read.All_: Subscribe to new call records (`POST /v1.0/subscriptions`).
* _CallRecords.Read.All_: Retrieve direct routing call records within the specified time range (`GET /v1.0/communications/callRecords/microsoft.graph.callRecords.getDirectRoutingCalls(fromDateTime={start date and time),toDateTime={end date and time))`)
* _CallRecord-PstnCalls.Read.All_: Retrieve PSTN call records within the specified time range (`GET /v1.0/communications/callRecords/microsoft.graph.callRecords.getPstnCalls(fromDateTime={start date and time),toDateTime={end date and time))`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

## Channel permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Channel.ReadBasic.All_ | Read the names and descriptions of channels. | Read channel names and channel descriptions, on behalf of the signed-in user.  | No | No |
| _Channel.Create_ | Create channels. | Create channels in any team, on behalf of the signed-in user.  | Yes | No |
| _Channel.Delete.All_ | Delete channels. | Delete channels in any team, on behalf of the signed-in user.  | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Channel.ReadBasic.All_ | Read the names and descriptions  of all channels. | Read all channel names and channel descriptions, without a signed-in user.  | Yes | No |
| _Channel.Create_ | Create channels. | Create channels in any team, without a signed-in user.  | Yes | No |
| _Channel.Delete.All_ | Delete channels. | Delete channels in any team, without a signed-in user.  | Yes | No |
|_Teamwork.Migrate.All_|Manage migration to Microsoft Teams|Creating and managing resources for migration to Microsoft Teams|Yes|Yes|

## Channel member permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_ChannelMember.Read.All_  |Read the members of channels. |Read the members of channels, on behalf of the signed-in user. |Yes | No |
|_ChannelMember.ReadWrite.All_ | Add and remove members from channels.| Add and remove members from channels, on behalf of the signed-in user. Also allows changing a member's role, for example from owner to non-owner.| Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_ChannelMember.Read.All_ |Read the members of all channels. |Read the members of all channels, without a signed-in user. |Yes | No |
|_ChannelMember.ReadWrite.All_ |Add and remove members from all channels.|Add and remove members from all channels, without a signed-in user. Also allows changing a member's role, for example from owner to non-owner.| Yes | No |

## Channel message permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_ChannelMessage.Edit_ (private preview)|Edit user's channel messages |Allows an app to edit channel messages in Microsoft Teams, on behalf of the signed-in user. |Yes | No |
|_ChannelMessage.Read.All_ |Read user channel messages  |Allows an app to read a channel's messages in Microsoft Teams, on behalf of the signed-in user. |Yes | No |
|_ChannelMessage.Send_ |Send channel messages |Allows an app to send channel messages in Microsoft Teams, on behalf of the signed-in user. |No| No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_ChannelMessage.Read.All_ |Read all channel messages  |Allows the app to read all channel messages in Microsoft Teams, without a signed-in user. |Yes | No |
|_ChannelMessage.UpdatePolicyViolation.All_ |Flag channel messages for violating policy |Allows the app to update Microsoft Teams channel messages by patching a set of Data Loss Prevention (DLP) policy violation properties to handle the output of DLP processing. | Yes | No |

> **Note:** See also [Group.Read.All](#group-permissions).

## Channel settings permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ChannelSettings.Read.All_ | Read the names, descriptions, and settings of channels. | Read all channel names, channel descriptions, and channel settings, on behalf of the signed-in user.| Yes | No |
| _ChannelSettings.ReadWrite.All_ | Read and write the names, descriptions, and settings of channels. | Read and write the names, descriptions, and settings of all channels, on behalf of the signed-in user.| Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ChannelSettings.Read.All_ | Read the names, descriptions, and settings of all channels. | Read all channel names, channel descriptions, and channel settings, without a signed-in user.| Yes | No |
| _ChannelSettings.ReadWrite.All_ | Read and write the names, descriptions, and settings of all channels. | Read and write the names, descriptions, and settings of all channels, without a signed-in user.| Yes | No |

## Chat permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_Chat.Read_ |Read your chat messages.  |Allows an app to read your 1:1 or group chat messages in Microsoft Teams, on your behalf. |No | No |
|_Chat.ReadBasic_ |Read names and members of user chat threads.  |Allows an app to read the members and descriptions of 1:1 and group chats threads, on behalf of the signed-in user. |No | No |
|_Chat.ReadWrite_ |Read your chat messages and send new ones.  |Allows an app to read and send your 1:1 or group chat messages in Microsoft Teams, on your behalf. |No | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_Chat.Read.WhereInstalled_ |Read all chat messages for chats where the associated Teams application is installed. |Allows the app to read all one-to-one or group chat messages in Microsoft Teams for chats where the associated Teams application is installed, without a signed-in user. | Yes | No |
|_Chat.Read.All_ |Read all chat messages.  |Allows the app to read all 1:1 or group chat messages in Microsoft Teams, without a signed-in user. |Yes | No |
|_Chat.ReadBasic.WhereInstalled_ |Read names and members of all chat threads where the associated Teams application is installed. |Allows the app to read names and members of all one-to-one and group chats in Microsoft Teams where the associated Teams application is installed, without a signed-in user. | Yes | No |
|_Chat.ReadBasic.All_ |Read names and members of user chat threads.  |Read names and members of all chat threads. |Yes | No |
|_Chat.UpdatePolicyViolation.All_ |Flag chat messages for violating policy. |Allows the app to update Microsoft Teams 1:1 or group chat messages by patching a set of Data Loss Prevention (DLP) policy violation properties to handle the output of DLP processing. | Yes | No |
|_Chat.ReadWrite.WhereInstalled_ |Read and write all chat messages for chats where the associated Teams application is installed. |Allows the app to read and write all chat messages in Microsoft Teams for chats where the associated Teams application is installed, without a signed-in user. | Yes | No |
|_Chat.ReadWrite.All_ |Read and write all chat messages. |Allows an app to read and write all one-to-one and group chats in Microsoft Teams, without a signed-in user. Does not allow sending messages. | Yes | No |

> **Note:** For messages in a channel, see [ChannelMessage permissions](#channel-message-permissions).

## Chat membership permissions

#### Delegated permissions

| Permission             | Display String                     | Description                                                  | Admin Consent Required | Microsoft Account supported |
| :--------------------- | :--------------------------------- | :----------------------------------------------------------- | :--------------------- | :-------------------------- |
| _ChatMember.Read_      | Read the members of chats.         | Read the members of chats on behalf of the signed-in user.   | Yes                    | No                          |
| _ChatMember.ReadWrite_ | Add and remove members from chats. | Add and remove members from chats on behalf of the signed-in user. | Yes                    | No                          |

#### Application permissions

| Permission                            | Display String                                               | Description                                                  | Admin Consent Required | Microsoft Account supported |
| :------------------------------------ | :----------------------------------------------------------- | :----------------------------------------------------------- | :--------------------- | :-------------------------- |
| _ChatMember.Read.WhereInstalled_      | Read the members of all chats where the associated Teams application is installed. | Allows the app to read the members of all chats where the associated Teams application is installed, without a signed-in user. | Yes                    | No                          |
| _ChatMember.Read.All_                 | Read the members of all chats.                               | Allows the app to read all 1:1 or group chat messages in Microsoft Teams, without a signed-in user. | Yes                    | No                          |
| _ChatMember.ReadWrite.WhereInstalled_ | Add and remove members from all chats where the associated Teams application is installed. | Allows the app to add and remove members from all chats where the associated Teams application is installed, without a signed-in user. | Yes                    | No                          |
| _ChatMember.ReadWrite.All_            | Add and remove members of all chats.                         | Read names and members of all chat threads.                  | Yes                    | No                          |

## Chat resource-specific consent permissions

#### Application permissions

| Permission                     | Display String                                                | Description  | Admin Consent Required | Microsoft Account supported |
|:-------------------------------|:--------------------------------------------------------------|:-------------|:-----------------------|:----------------------------|
| _ChatSettings.Read.Chat_         | Read this chat's settings.                                    | Allows the app to read this chat's settings, without a signed-in user. |No | No |
| _ChatSettings.ReadWrite.Chat_    | Read and write this chat's settings.                          | Allows the app to read and write this chat's settings, without a signed-in user. |No | No |
| _ChatMessage.Read.Chat_          | Read this chat's messages.                                    | Allows the app to read this chat's messages, without a signed-in user. |No | No |
| _ChatMember.Read.Chat_           | Read this chat's members.                                     | Allows the app to read this chat's members, without a signed-in user. |No | No |
| _Chat.Manage.Chat_               | Manage this chat.                                             | Allows the app to manage the chat, the chat's members, and grant access to the chat's data, without a signed-in user.  |No | No |
| _TeamsTab.Read.Chat_             | Read this chat's tabs.                                        | Allows the app to read this chat's tabs, without a signed-in user. |No | No |
| _TeamsTab.Create.Chat_           | Create tabs in this chat.                                     | Allows the app to create tabs in this chat, without a signed-in user. |No | No |
| _TeamsTab.Delete.Chat_           | Delete this chat's tabs.                                      | Allows the app to delete this chat's tabs, without a signed-in user. |No | No |
| _TeamsTab.ReadWrite.Chat_        | Manage this chat's tabs.                                      | Allows the app to manage this chat's tabs, without a signed-in user. |No | No |
| _TeamsAppInstallation.Read.Chat_ | Read which apps are installed in this chat.                   | Allows the app to read the Teams apps that are installed in this chat along with the permissions granted to each app, without a signed-in user.  |No | No |
| _OnlineMeeting.ReadBasic.Chat_   | Read basic properties of a meeting associated with this chat. | Allows the app to read basic properties—such as name, schedule, organizer, and join link—of a meeting associated with this chat, without a signed-in user. |No | No |
| _Calls.AccessMedia.Chat_         | Access media streams in calls associated with this chat or meeting.                                    | Allows the app to access media streams in calls associated with this chat or meeting, without a signed-in user. |No | No |
| _Calls.JoinGroupCalls.Chat_         | Join calls associated with this chat or meeting.                                    | Allows the app to join calls associated with this chat or meeting, without a signed-in user. |No | No |
| _TeamsActivity.Send.Chat_        | Send activity feed notifications to users in this chat.       | Allows the app to create new notifications in the teamwork activity feeds of the users in this chat, without a signed-in user. | No | No |

>[!NOTE]
> Currently, these permissions are supported only in the beta version of Microsoft Graph.

## ChatMessage permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ChatMessage.Send_ | Send user chat messages | Allows an app to send 1:1 and group chat messages in Microsoft Teams, on behalf of the signed-in user. | No | No |

---

## Cloud PC permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_CloudPC.Read.All_ | Read Cloud PCs | Allows the app to read Cloud PC objects such as provisioning policies, on behalf of the signed-in user. | No | No |
|_CloudPC.ReadWrite.All_ | Read and write Cloud PCs | Allows the app to create, read, update, and delete Cloud PC objects such as Azure network connections, provisioning policies, and device images, on behalf of the user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_CloudPC.Read.All_ | Read Cloud PCs | Allows the app to read Cloud PC objects such as provisioning policies, without a signed-in user. | Yes | No |
|_CloudPC.ReadWrite.All_ | Read and write Cloud PCs | Allows the app to create, read, update, and delete Cloud PC objects such as Azure network connections, provisioning policies, and device images, without a signed-in user. | Yes | No |

### Example usage

#### Delegated

* _CloudPC.Read.All_: View the properties of all Cloud PCs (`GET /deviceManagement/virtualEndpoint/cloudPCs`).
* _CloudPC.ReadWrite.All_: Edit the Cloud PC provisioning policy (`PATCH /deviceManagement/virtualEndpoint/provisioningPolicies/{id}`).

#### Application

* _CloudPC.Read.All_: View the properties of all Cloud PCs (`GET /deviceManagement/virtualEndpoint/cloudPCs`).
* _CloudPC.ReadWrite.All_: Edit the Cloud PC provisioning policy (`PATCH /deviceManagement/virtualEndpoint/provisioningPolicies/{id}`).

---

## Consent requests permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_ConsentRequest.Read.All_ |Read consent requests |Allows the app to read consent requests and approvals on behalf of the signed-in user. |Yes | No |
|_ConsentRequest.ReadWrite.All_ |Read and write consent requests |Allows the app to read app consent requests and approvals, and deny or approve those requests on behalf of the signed-in user. |Yes | No |

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
|_ConsentRequest.Read.All_ |Read consent requests |Allows the app to read app consent requests and approvals without a signed-in user. |Yes |
|_ConsentRequest.ReadWrite.All_ |Read and write consent requests |Allows the app to read app consent requests and approvals, and deny or approve those requests without a signed-in user. |Yes |

## Cross-tenant user profile sharing permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_CrossTenantUserProfileSharing.Read_ |Read shared cross-tenant user profile and export data  |Allows the application to list and query user profile information associated with the current tenant on behalf of the signed-in user.  It also permits the application to export external user data (e.g. customer content or system-generated logs), associated with the current tenant on behalf of the signed-in user. |Yes | Yes |
|_CrossTenantUserProfileSharing.Read.All_ |Read all shared cross-tenant user profiles and export their data  |Allows the application to list and query any shared user profile information associated with the current tenant on behalf of the signed-in user.  It also permits the application to export external user data (e.g. customer content or system-generated logs), for any user associated with the current tenant on behalf of the signed-in user. |Yes | Yes |
|_CrossTenantUserProfileSharing.ReadWrite_ |Read shared cross-tenant user profile and export or delete data |Allows the application to list and query user profile information associated with the current tenant on behalf of the signed-in user.  It also permits the application to export and remove external user data (e.g. customer content or system-generated logs), associated with the current tenant on behalf of the signed-in user. |Yes |No|
|_CrossTenantUserProfileSharing.ReadWrite.All_ |Allows the application to list and query any shared user profile information associated with the current tenant on behalf of the signed-in user.  It also permits the application to export and remove external user data (e.g. customer content or system-generated logs), for any user associated with the current tenant on behalf of the signed-in user. |Yes |No|

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
|_CrossTenantUserProfileSharing.Read.All_ |Allows the application to list and query any shared user profile information associated with the current tenant without a signed-in user.  It also permits the application to export external user data (e.g. customer content or system-generated logs), for any user associated with the current tenant without a signed-in user. | Yes |
|_CrossTenantUserProfileSharing.ReadWrite.All_ |Allows the application to list and query any shared user profile information associated with the current tenant without a signed-in user.  It also permits the application to export and remove external user data (e.g. customer content or system-generated logs), for any user associated with the current tenant without a signed-in user. |Yes|

## Contacts permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_Contacts.Read_ |Read user contacts  |Allows the app to read user contacts. |No | Yes |
|_Contacts.Read.Shared_ |Read user and shared contacts |Allows the app to read contacts that the user has permissions to access, including the user's own and shared contacts. |No |No|
|_Contacts.ReadWrite_ |Have full access to user contacts |Allows the app to create, read, update, and delete user contacts. |No |Yes|
|_Contacts.ReadWrite.Shared_ |Read and write user and shared contacts |Allows the app to create, read, update and delete contacts that the user has permissions to, including the user's own and shared contacts. |No |No|

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
|_Contacts.Read_ |Read contacts in all mailboxes |Allows the app to read all contacts in all mailboxes without a signed-in user. |Yes |
|_Contacts.ReadWrite_ |Read and write contacts in all mailboxes |Allows the app to create, read, update, and delete all contacts in all mailboxes without a signed-in user. |Yes |

> **Important**
Administrators can configure [application access policy](auth-limit-mailbox-access.md) to limit app access to _specific_ mailboxes and not all the mailboxes in the organization, even if the app has been granted the application permissions of Contacts.Read or Contacts.ReadWrite.

### Example usage
#### Delegated

* _Contacts.Read_: Read a contact from one of the top-level contact folders of the signed-in user (`GET /me/contactfolders/{Id}/contacts/{id}`).
* _Contacts.ReadWrite_: Update the contact photo of one of the signed-in user's contacts (`PUT /me/contactfolders/{contactFolderId}/contacts/{id}/photo/$value`).
* _Contacts.ReadWrite_: Add contacts to the root folder of the signed-in user (`POST /me/contacts`).

#### Application

* _Contacts.Read_: Read contacts from one of the top-level contact folders of any user in the organization (`GET /users/{id | userPrincipalName}/contactfolders/{Id}/contacts/{id}`).
* _Contacts.ReadWrite_: Update the photo for any contact of any user in an organization (`PUT /users/{id | userPrincipalName}/contactfolders/{contactFolderId}/contacts/{id}/photo/$value`).
* _Contacts.ReadWrite_: Add contacts to the root folder of any user in the organization (`POST /users/{id | userPrincipalName}/contacts`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Custom security attributes permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _CustomSecAttributeAssignment.Read.All_ | Read custom security attribute assignments | Allows the app to read custom security attribute assignments for all principals in the tenant on behalf of a signed in user. | Yes | No |
| _CustomSecAttributeAssignment.ReadWrite.All_ | Read and write custom security attribute assignments | Allows the app to read and write custom security attribute assignments for all principals in the tenant on behalf of a signed in user. | Yes | No |
| _CustomSecAttributeDefinition.Read.All_ | Read custom security attribute definitions | Allows the app to read custom security attribute definitions for the tenant on behalf of a signed in user. | Yes | No |
| _CustomSecAttributeDefinition.ReadWrite.All_ | Read and write custom security attribute definitions | Allows the app to read and write custom security attribute definitions for the tenant on behalf of a signed in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _CustomSecAttributeAssignment.Read.All_ | Read custom security attribute assignments | Allows the app to read custom security attribute assignments for all principals in the tenant without a signed in user. | Yes |
| _CustomSecAttributeAssignment.ReadWrite.All_ | Read and write custom security attribute assignments | Allows the app to read and write custom security attribute assignments for all principals in the tenant without a signed in user. | Yes |
| _CustomSecAttributeDefinition.Read.All_ | Read custom security attribute definitions | Allows the app to read custom security attribute definitions for the tenant without a signed in user. | Yes |
| _CustomSecAttributeDefinition.ReadWrite.All_ | Read and write custom security attribute definitions | Allows the app to read and write custom security attribute definitions for the tenant without a signed in user. | Yes |

---

## Device local credential permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _DeviceLocalCredential.ReadBasic.All_ | Read basic device local credential information | Allows the app to read device local credential properties excluding passwords, on behalf of the signed-in user. | Yes | No |
| _DeviceLocalCredential.Read.All_ | Read device local credential information | Allows the app to read device local credential properties including passwords, on behalf of the signed-in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _DeviceLocalCredential.ReadBasic.All_ | Read basic device local credential information | Allows the app to read device local credential properties excluding passwords. | Yes | No |
| _DeviceLocalCredential.Read.All_ | Read device local credential information | Allows the app to read device local credential properties including passwords. | Yes | No |

### Example usage

#### Delegated

* DeviceLocalCredential.ReadBasic.All_: List the device local credential for all devices in the tenant without returning the 'credentials' property (`GET /deviceLocalCredentials`).
* DeviceLocalCredential.Read.All_: Get a device local credential with the local administrator account password in Base64 encoded value (`GET /deviceLocalCredentials/{deviceId}?$select=credentials`).

#### Application

* DeviceLocalCredential.ReadBasic.All_: List the device local credential for all devices in the tenant without returning the 'credentials' property (`GET /deviceLocalCredentials`).
* DeviceLocalCredential.Read.All_: Get a device local credential with the local administrator account password in Base64 encoded value (`GET /deviceLocalCredentials/{deviceId}?$select=credentials`).

---

## Granular delegated admin privileges (GDAP) permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _DelegatedAdminRelationship.Read.All_ | Read Delegated Admin relationships with customers | Allows the app to read details of delegated admin relationships with customers like access details (that includes roles) and the duration as well as specific role assignments to security groups on behalf of the signed-in user. | Yes | No |
| _DelegatedAdminRelationship.ReadWrite.All_ | Manage Delegated Admin relationships with customers | Allows the app to manage (create-update-terminate) Delegated Admin relationships with customers and role assignments to security groups for active Delegated Admin relationships on your behalf. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _DelegatedAdminRelationship.Read.All_ | Read Delegated Admin relationships with customers | Allows the app to read details of delegated admin relationships with customers like access details (that includes roles) and the duration as well as specific role assignments to security groups without a signed-in user. | Yes | No |
| _DelegatedAdminRelationship.ReadWrite.All_ | Manage Delegated Admin relationships with customers | Allows the app to manage (create-update-terminate) Delegated Admin relationships with customers and role assignments to security groups for active Delegated Admin relationships without a signed-in user. | Yes | No |

---

## Device permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_Device.Read_ |Read user devices |Allows the app to read a user's list of devices on behalf of the signed-in user. |No | Yes |
|_Device.Read.All_ |Read all devices |Allows the app to read your organization's devices' configuration information on behalf of the signed-in user.|Yes | Yes |
|_Device.Command_ |Communicate with user devices |Allows the app to launch another app or communicate with another app on a user's device on behalf of the signed-in user. |No | Yes |


#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
|_Device.Read.All_ |Read all devices |Allows the app to read your organization's devices' configuration information without a signed-in user. |Yes |
|_Device.ReadWrite.All_ |Read and write devices |Allows the app to read and write all device properties without a signed in user. Does not allow device creation or update of device alternative security identifiers. |Yes |

> [!NOTE]
> Before December 3rd, 2020, when the application permission *Device.ReadWrite.All* was granted, the [Device Managers](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#deprecated-roles) directory role was also assigned to the app's service principal. This directory role assignment is not removed automatically when the associated application permissions is revoked. To ensure that an application's access to read or write to devices is removed, customers must also remove any related directory roles that were granted to the application.
> 
> A service update disabling this behavior began rolling out on December 3rd, 2020. Deployment to all customers completed on January 11th, 2021. Directory roles are no longer automatically assigned when application permissions are granted.

### Example usage

#### Application

* _Device.ReadWrite.All_: Read all registered devices in the organization (`GET /devices`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Directory permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Directory.Read.All_ |Read directory data | Allows the app to read data in your organization's directory, such as users, groups and apps. **Note**: Users may consent to applications that require this permission if the application is registered in their own organization's tenant.| Yes | No |
| _Directory.ReadWrite.All_ |Read and write directory data | Allows the app to read and write data in your organization's directory, such as users, and groups. It does not allow the app to delete users or groups, or reset user passwords. | Yes | No |
| _Directory.AccessAsUser.All_ |Access directory as the signed-in user  | Allows the app to have the same access to information in the directory as the signed-in user. | Yes | No |

<br/>

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Directory.Read.All_ | Read directory data | Allows the app to read data in your organization's directory, such as users, groups and apps, without a signed-in user. | Yes |
| _Directory.ReadWrite.All_ | Read and write directory data | Allows the app to read and write data in your organization's directory, such as users, and groups, without a signed-in user. Does not allow user or group deletion. | Yes |

### Remarks

Directory permissions provide the highest level of privilege for accessing directory resources such as [user](/graph/api/resources/user), [group](/graph/api/resources/group), and [device](/graph/api/resources/device) in an organization.

They also exclusively control access to other directory resources like: [organizational contacts](/graph/api/resources/orgcontact?view=graph-rest-beta&preserve-view=true), [schema extension APIs](/graph/api/resources/schemaextension?view=graph-rest-beta&preserve-view=true), [Privileged Identity Management (PIM) APIs](/graph/api/resources/privilegedidentitymanagement-root?view=graph-rest-beta&preserve-view=true), as well as many of the resources and APIs listed under the **Azure Active Directory** node in the v1.0 and beta API reference documentation. These include administrative units, directory roles, directory settings, policy, and many more.

> [!NOTE]
> Before December 3rd, 2020, when the application permission *Directory.Read.All* was granted, the [Directory Readers](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#directory-readers-permissions) directory role was also assigned to the app's service principal. When *Directory.ReadWrite.All* was granted, the [Directory Writers](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#directory-writers-permissions) directory role was also assigned. These directory roles are not removed automatically when the associated application permissions are revoked. To remove an application's access to read or write to the directory, customers must also remove any directory roles that were granted to the application.
> 
> A service update disabling this behavior began rolling out on December 3rd, 2020. Deployment to all customers completed on January 11th, 2021. Directory roles are no longer automatically assigned when application permissions are granted.

The _Directory.ReadWrite.All_ permission grants the following privileges:

- Full read of all directory resources (both declared properties and navigation properties)
- Create and update users
- Disable and enable users (but not Company Administrator)
- Set user alternative security ID (but not administrators)
- Create and update groups
- Manage group memberships
- Update group owner
- Manage license assignments
- Define schema extensions on applications
- Manage directory settings
- Manage admin consent workflow configuration (but not whether admin consent is required or who is authorized to grant admin consent)

> **Note**:
> - No rights to reset user passwords.
> - Updating another user's **businessPhones**, **mobilePhone**, or **otherMails** property is only allowed on users who are non-administrators or assigned one of the following roles: Directory Readers, Guest Inviter, Message Center Reader and Reports Reader. For more details, see Helpdesk (Password) Administrator in [Azure AD available roles](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).  This is the case for apps granted either the User.ReadWrite.All or Directory.ReadWrite.All delegated or application permissions.
> - No rights to delete resources (including users or groups).
> - Specifically excludes create or update for resources not listed above. This includes: application, oAuth2PermissionGrant, appRoleAssignment, device, servicePrincipal, organization, domains, and so on.


### Example usage

#### Delegated
* _Directory.Read.All_: List all administrative units in an organization (`GET /beta/administrativeUnits`)
* _Directory.ReadWrite.All_: Add members to a directory role (`POST /directoryRoles/{id}/members/$ref`)

#### Application
* _Directory.Read.All_: List all memberships of a user, including directory roles and administrative units (`GET /beta/users/{id}/memberOf`)
* _Directory.Read.All_: List all group members, including service principals (`GET /beta/groups/{id}/members`)
* _Directory.ReadWrite.All_: Add an owner to a group (`POST /groups/{id}/owners/$ref`)


For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Directory recommendations permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _DirectoryRecommendations.Read.All_ | Read all recommendations | Allows the  app to read recommendations on behalf of the signed-in user. | Yes | No |
| _DirectoryRecommendations.ReadWrite.All_ | Manage all recommendations | Allows the  app to read and write recommendations on behalf of the signed-in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _DirectoryRecommendations.Read.All_ | Read all recommendations | Allows the  app to read recommendations without a signed-in user. | Yes |
| _DirectoryRecommendations.ReadWrite.All_ | Manage all recommendations | Allows the  app to read and write recommendations without a signed-in user. | Yes |

---

## Domain permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_Domain.Read.All_ |Read domains|Allows the app to read all domain properties on behalf of the signed-in user. |Yes | No |
|_Domain.ReadWrite.All_ | Read and write domains |Allows the app to read and write all domain properties on behalf of the signed-in user. Also allows the app to add, verify, and remove domains. |Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Domain.Read.All_ | Read domains | Allows the app to read all domain properties without a signed-in user. | Yes |
| _Domain.ReadWrite.All_ | Read and write domains | Allows the app to read and write domains without a signed-in user. | Yes |

---

## eDiscovery permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_eDiscovery.Read.All_ |Read user eDiscovery case data |Allows the app to read eDiscovery objects such as cases, custodians, review sets and other related objects on behalf of the signed-in user. |Yes | No |
|_eDiscovery.ReadWrite.All_ | Read and write eDiscovery case data |Allows the app to read and write eDiscovery objects such as cases, custodians, review sets and other related objects on behalf of the signed-in user. |Yes | No |

#### Application permissions

None

### Example usage

#### Delegated

* _eDiscovery.Read.All_: Get the list of cases available to the user (`GET /compliance/ediscovery/cases`)
* _eDiscovery.ReadWrite.All_: Create a reviewset query in a review set (`POST /compliance/ediscovery/cases/{caseId}/reviewSets/{reviewSetId}/queries`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---


## Education permissions

#### Delegated permissions

| Permission                      | Display String                                                   | Description                                                                                                                                                                                                                                                                      | Admin Consent Required | Microsoft Account supported |
| :------------------------------ | :--------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------- | :-------------------------- |
| _EduAdministration.Read_        | Read education app settings                                      | Allows the app to read education app settings on behalf of the user.                                                                                                                                                                                                             | Yes                    | No                          |
| _EduAdministration.ReadWrite_   | Manage education app settings                                    | Allows the app to manage education app settings on behalf of the user.                                                                                                                                                                                                           | Yes                    | No                          |
| _EduAssignments.ReadBasic_      | Read users' class assignments without grades                     | Allows the app to read assignments without grades on behalf of the user                                                                                                                                                                                                          | Yes                    | No                          |
| _EduAssignments.ReadWriteBasic_ | Read and write users' class assignments without grades           | Allows the app to read and write assignments without grades on behalf of the user                                                                                                                                                                                                | Yes                    | No                          |
| _EduAssignments.Read_           | Read users' view of class assignments and their grades           | Allows the app to read assignments and their grades on behalf of the user                                                                                                                                                                                                        | Yes                    | No                          |
| _EduAssignments.ReadWrite_      | Read and write users' view of class assignments and their grades | Allows the app to read and write assignments and their grades on behalf of the user                                                                                                                                                                                              | Yes                    | No                          |
| _EduRoster.ReadBasic_           | Read a limited subset of users' view of the roster               | Allows the app to read a limited subset of the properties from the structure of schools and classes in an organization's roster and a limited subset of properties about users to be read on behalf of the user. Includes name, status, education role, and email address. | Yes                    | No                          |
| _EduRoster.Read_                | Read users' view of the roster                                   | Allows the app to read the structure of schools and classes in an organization's roster and education-specific information about users to be read on behalf of the user.                                                                                                         | Yes                    |
| _EduRoster.ReadWrite_           | Read and write users' view of the roster                         | Allows the app to read and write the structure of schools and classes in an organization's roster and education-specific information about users to be read and written on behalf of the user.                                                                                   | Yes                    |

#### Application permissions

| Permission                          | Display String                                      | Description                                                                                                                                                                   | Admin Consent Required |
| :---------------------------------- | :-------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------- |
| _EduAdministration.Read.All_        | Read Education app settings                         | Read the state and settings of all Microsoft education apps on behalf of the user.                                                                                             | Yes                    |
| _EduAdministration.ReadWrite.All_   | Manage education app settings                       | Manage the state and settings of all Microsoft education apps on behalf of the user.                                                                                           | yes                    |
| _EduAssignments.ReadBasic.All_      | Read all class assignments without grades           | Allows the app to read all class assignments without grades for all users without a signed-in user.                                                                         | Yes                    |
| _EduAssignments.ReadWriteBasic.All_ | Create, read, update, and delete all class assignments without grades              | Allows the app to create, read, update and delete all class assignments without grades for all users without a signed-in user.          | Yes                    |
| _EduAssignments.Read.All_           | Read all class assignments with grades              | Allows the app to read all class assignments with grades for all users without a signed-in user.                                                                    | Yes                    |
| _EduAssignments.ReadWrite.All_      | Create, read, update, and delete all class assignments with grades            | Allows the app to create, read, update and delete all class assignments with grades for all users without a signed-in user.                    | Yes                    |
| _EduRoster.ReadBasic.All_           | Read a limited subset of the organization's roster. | Allows the app to read a limited subset of both the structure of schools and classes in an organization's roster and education-specific information about all users.          | Yes                    |
| _EduRoster.Read.All_                | Read the organization's roster.                     | Allows the app to read the structure of schools and classes in the organization's roster and education-specific information about all users to be read.                       | Yes                    |
| _EduRoster.ReadWrite.All_           | Read and write the organization's roster.           | Allows the app to read and write the structure of schools and classes in the organization's roster and education-specific information about all users to be read and written. | Yes                    |

### Example usage

#### Delegated

* _EduAssignments.Read_: Get the signed-in student's assignment information (`GET /education/classes/{id}/assignments/{id}`)
* _EduAssignments.ReadWriteBasic_: Submit signed-in student assignment (`GET /education/classes/{id}/assignments/{id}submit`)
* _EduRoster.ReadBasic_: Classes a signed-in user attends or teaches (`GET /education/classes/{id}/members`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).


---

## Employee learning permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _LearningContent.Read.All_ |    Read learning content | Allows the app to read learning content in the organization's directory, on behalf of the signed-in user. | Yes | No |
| _LearningContent.ReadWrite.All_  |    Manage learning content | Allows the app to manage all learning content in the organization's directory, on behalf of the signed-in user. | Yes | No |
| _LearningProvider.Read_ |    Read learning provider | Allows the app to read data for the learning provider in the organization's directory, on behalf of the signed-in user. | Yes | No |
| _LearningProvider.ReadWrite_  |    Manage learning provider | Allows the app to create, update, read, and delete data for the learning provider in the organization's directory, on behalf of the signed-in user. | Yes | No |
| _LearningAssignedCourse.Read_  |    Read assignment | Allows the app to read data for assignment record in organization's directory on behalf of the signed-in user. | Yes | No |
| _LearningSelfInitiatedCourse.Read_  |    Read self-initiated course | Allows the app to read data for self-initiated course record in organization's directory on behalf of the signed-in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _LearningContent.Read.All_ |    Read all learning content | Allows the app to read all learning content in the organization's directory, without a signed-in user. | Yes | No |
| _LearningContent.ReadWrite.All_  |    Manage all learning content | Allows the app to manage all learning content in the organization's directory, without a signed-in user. | Yes | No |
| _LearningAssignedCourse.Read.All_ |    Read learning assignment | Allows the app to read data for learning assignment record in organization's directory, without a signed-in user. | Yes | No |
| _LearningSelfInitiatedCourse.Read.All_ |    Read learning self-initiated course| Allows the app to read data for learning self-initiated course record in organization's directory, without a signed-in user. | Yes | No |
| _LearningAssignedCourse.ReadWrite.All_ |    Manage all learning assignment for learner | Allows the app to create/read/update/delete data for learning assignment record in organization's directory, without a signed-in user. | Yes | No |
| _LearningSelfInitiatedCourse.ReadWrite.All_ |    Manage all self-initiated course for learner | Allows the app to create/read/update/delete data for self-initiated course record in organization's directory, without a signed-in user. | Yes | No |


---

## Entitlement management permissions

#### Delegated permissions

|Permission|Display String|Description|Admin Consent Required|
|:----------|:--------------|:-----------|:-------|
|_EntitlementManagement.ReadWrite.All_|Read and write entitlement management resources|Allows the app to request access to read and manage access packages and related entitlement management resources on behalf of the signed-in user.|Yes|
|_EntitlementManagement.Read.All_|Read entitlement management resources|Allows the app to request access to read access packages and related entitlement management resources on behalf of the signed-in user.|Yes|

#### Application permissions

|Permission|Display String|Description|Admin Consent Required|
|:----------|:--------------|:-----------|:-------|
|_EntitlementManagement.ReadWrite.All_|Read and write entitlement management resources|Allows the app to read and manage access packages and related entitlement management resources.|Yes|
|_EntitlementManagement.Read.All_|Read entitlement management resources|Allows the app to read access packages and related entitlement management resources.|Yes|

## Files permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Files.Read_ | Read user files | Allows the app to read the signed-in user's files. | No | Yes |
| _Files.Read.All_ | Read all files that user can access | Allows the app to read all files the signed-in user can access. | No | Yes |
| _Files.ReadWrite_  | Have full access to user files | Allows the app to read, create, update, and delete the signed-in user's files. | No| Yes |
| _Files.ReadWrite.All_ | Have full access to all files user can access | Allows the app to read, create, update, and delete all files the signed-in user can access. | No | Yes |
| _Files.ReadWrite.AppFolder_ | Have full access to the application's folder (preview) | (Preview) Allows the app to read, create, update, and delete files in the application's folder. | No | Yes |
| _Files.Read.Selected_  | Read files that the user selects | **Limited support in Microsoft Graph; see Remarks** <br/> (Preview) Allows the app to read files that the user selects. The app has access for several hours after the user selects a file.  | No | No |
| _Files.ReadWrite.Selected_ | Read and write files that the user selects | **Limited support in Microsoft Graph; see Remarks** <br/> (Preview) Allows the app to read and write files that the user selects. The app has access for several hours after the user selects a file. | No | No |

#### Application permissions

| Permission | Display String | Description | Admin Consent Required |
| :--------- | :------------- | :---------- | :--------------------- |
| _Files.Read.All_ | Read files in all site collections | Allows the app to read all files in all site collections without a signed in user.  | Yes |
| _Files.ReadWrite.All_ | Read and write files in all site collections | Allows the app to read, create, update, and delete all files in all site collections without a signed in user. | Yes |

### Remarks

> **Note**: For personal accounts, Files.Read and Files.ReadWrite also grant access to files shared with the signed-in user.

The Files.Read.Selected and Files.ReadWrite.Selected delegated permissions are only valid on work or school accounts and are only exposed for working with [Office 365 file handlers (v1.0)](/previous-versions/office/office-365-api/).
They should not be used for directly calling Microsoft Graph APIs.

The Files.ReadWrite.AppFolder delegated permission is only valid for personal accounts and is used for accessing the [App Root special folder](https://dev.onedrive.com/misc/appfolder.htm) with the OneDrive [Get special folder](/graph/api/drive-get-specialfolder) Microsoft Graph API.


### Example usage

#### Delegated

* _Files.Read_: Read files stored in the signed-in user's OneDrive (`GET /me/drive/root/children`)
* _Files.Read.All_: Read files shared with the signed-in user (`GET /me/drive/root/sharedWithMe`)
* _Files.ReadWrite_: Write a file in the signed-in user's OneDrive (`PUT /me/drive/root/children/filename.txt/content`)
* _Files.ReadWrite.All_: Write a file shared with the user (`PUT /users/rgregg@contoso.com/drive/root/children/file.txt/content`)
* _Files.ReadWrite.AppFolder_: Write files into the app's folder in OneDrive (`PUT /me/drive/special/approot/children/file.txt/content`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---
## Financials permissions
#### Delegated permissions

|Permission|Display String|Description|Admin Consent Required|
|:----------|:--------------|:-----------|:-------|
|_Financials.ReadWrite.All_|Read and write financials data|Allows the app to read and write financials data on behalf of the signed-in user|No|

## Group permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Group.Read.All_ |    Read all groups | Allows the app to list groups, and to read their properties and all group memberships on behalf of the signed-in user.  Also allows the app to read calendar, conversations, files, and other group content for all groups the signed-in user can access. | Yes | No |
| _Group.ReadWrite.All_ |    Read and write all groups| Allows the app to create groups and read all group properties and memberships on behalf of the signed-in user.  Also allows the app to read and write calendar, conversations, files, and other group content for all groups the signed-in user can access. Additionally allows group owners to manage their groups and allows group members to update group content. | Yes | No |
| _GroupMember.Read.All_ |    Read group memberships | Allows the app to list groups, read basic group properties and read membership of all groups the signed-in user has access to. | Yes | No |
| _GroupMember.ReadWrite.All_ |    Read and write group memberships | Allows the app to list groups, read basic properties, read and update the membership of the groups the signed-in user has access to. Group properties and owners cannot be updated and groups cannot be deleted. | Yes | No |
| _UnifiedGroupMember.Read.AsGuest_ |    Read unified (Microsoft 365) group memberships as a guest user | Allows the app to read basic unified group properties, memberships, and owners of the group the signed-in guest is a member of. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Group.Read.All_ | Read all groups | Allows the app to read group properties and memberships, and read conversations for all groups, without a signed-in user. | Yes |
| _Group.ReadWrite.All_ | Read and write all groups | Allows the app to create groups, read all group properties and memberships, update group properties and memberships, and delete groups. Also allows the app to read and write conversations. All of these operations can be performed by the app without a signed-in user.| Yes |
| _GroupMember.Read.All_ |    Read group memberships | Allows the app to read memberships and basic group properties for all groups without a signed-in user. | Yes |
| _GroupMember.ReadWrite.All_ |    Read and write group memberships | Allows the app to list groups, read basic properties, read and update the membership of the groups without a signed-in user. Group properties and owners cannot be updated and groups cannot be deleted. | Yes |
| _Group.Create_ |    Create groups | Allows the calling app to create groups without a signed-in user. Does not allow read, update, or deletion of any groups. | Yes |

### Remarks

Group functionality is not supported on personal Microsoft accounts.

For Microsoft 365 groups, Group permissions grant the app access to the contents of the group; for example, conversations, files, notes, and so on.

For application permissions, there are some limitations for the APIs that are supported. For more information, see [known issues](known-issues.md).

In some cases, an app may need [Directory permissions](#directory-permissions) to read some group properties like `member` and `memberOf`. For example, if a group has a one or more [servicePrincipals](/graph/api/resources/serviceprincipal?view=graph-rest-beta&preserve-view=true) as members, the app will need effective permissions to read service principals through being granted one of the _Directory.\*_ permissions, otherwise Microsoft Graph will return an error. (In the case of delegated permissions, the signed-in user will also need sufficient privileges in the organization to read service principals.) The same guidance applies for the `memberOf` property, which can return [administrativeUnits](/graph/api/resources/administrativeunit?view=graph-rest-beta&preserve-view=true).

To set a Microsoft 365 group's **preferredDataLocation** attribute, an app needs Directory.ReadWrite.All permission. When users in a multi-geo environment create a Microsoft 365 group, the **preferredDataLocation** value for the group is automatically set to that of the user. For more information about groups' preferred data location, see [Create a Microsoft 365 group with a specific PDL](/office365/enterprise/multi-geo-add-group-with-pdl).

Group permissions are used to control access to [Microsoft Teams](/graph/api/resources/teams-api-overview) resources and APIs. Personal Microsoft accounts are not supported.

Group permissions are also used to control access to [Microsoft Planner](/graph/api/resources/planner-overview) resources and APIs. Only delegated permissions are supported for Microsoft Planner APIs; application permissions are not supported. Personal Microsoft accounts are not supported.


### Example usage
#### Delegated

* _Group.Read.All_: Read all Microsoft 365 groups that the signed-in user is a member of (`GET /me/memberOf/$/microsoft.graph.group?$filter=groupTypes/any(a:a%20eq%20'unified')`).
* _Group.Read.All_: Read all Microsoft 365 group content like conversations (`GET /groups/{id}/conversations`).
* _Group.ReadWrite.All_: Update group properties, like photo (`PUT /groups/{id}/photo/$value`).
* _GroupMember.ReadWrite.All_: Update group members (`POST /groups/{id}/members/$ref`).
> **Note:**: This also requires _User.ReadBasic.All_ to read the user to add as a member.

#### Application

* _Group.Read.All_: Find all groups with name that starts with 'Sales' (`GET /groups?$filter=startswith(displayName,'Sales')`).
* _Group.ReadWrite.All_: Daemon service creates new events on a Microsoft 365 group's calendar (`POST /groups/{id}/events`).
* _Group.Create_: Creates a new group (`POST /groups`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---


## Identity provider permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _IdentityProvider.Read.All_ |   Read identity provider information  | Allows the app to read identity providers configured in your Azure AD or Azure AD B2C tenant on behalf of the signed-in user. | Yes | No |
| _IdentityProvider.ReadWrite.All_ |   Read and write identity provider information  |  Allows the app to read or write identity providers configured in your Azure AD or Azure AD B2C tenant on behalf of the signed-in user. | Yes | No |

### Remarks

_IdentityProvider.Read.All_ and _IdentityProvider.ReadWrite.All_ are valid only for work or school accounts. For an app to read or write identity providers with delegated permissions, the signed-in user must be assigned the Global Administrator role. For more information about administrator roles, see [Assigning administrator roles in Azure Active Directory](/azure/active-directory/active-directory-assign-admin-roles).

### Example usage

#### Delegated
The following usages are valid for both delegated permissions:

* _IdentityProvider.Read.All_: Read all identity providers configured in the tenant (`GET /beta/identityProviders`)
* _IdentityProvider.Read.All_: Read an existing identity provider (`GET /beta/identityProviders/{id}`)
* _IdentityProvider.ReadWrite.All_ Create an identity provider (`POST /beta/identityProviders`)
* _IdentityProvider.ReadWrite.All_ Update an existing identity provider (`PATCH /beta/identityProviders/{id}`)
* _IdentityProvider.ReadWrite.All_ Delete an existing identity provider (`DELETE /beta/identityProviders/{id}`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Identity protection risk permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _IdentityRiskEvent.Read.All_ |   Read identity risk event information  | Allows the app to read identity risk event information for all users in your organization on behalf of the signed-in user. | Yes | No |
| _IdentityRiskyUser.Read.All_ |   Read identity user risk  information  | Allows the app to read identity user risk information for all users in your organization on behalf of the signed-in user. | Yes | No |
| _IdentityRiskyUser.ReadWrite.All_ |   Read and update identity user risk  information  | Allows the app to read and update identity user risk information for all users in your organization on behalf of the signed-in user. | Yes | No |
| _IdentityRiskyServicePrincipal.Read.All_ |   Read all risky service principal information  | Allows the app to read all risky service principal information for your organization, on behalf of the signed-in user. | Yes | No |
| _IdentityRiskyServicePrincipal.ReadWrite.All_ |   Read and write all risky service principal information  | Allows the app to read and update risky service principal information for all service principals in your organization, on behalf of the signed-in user. Update operations include dismissing risky service principals.| Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _IdentityRiskEvent.Read.All_ |   Read identity risk event information | Allows the app to read identity risk event information for all users in your organization without a signed-in user. | Yes |
| _IdentityRiskyUser.Read.All_ |   Read identity user risk  information | Allows the app to read identity user risk information for all users in your organization without a signed-in user. | Yes |
| _IdentityRiskyUser.ReadWrite.All_ |   Read and update identity user risk  information | Allows the app to read and update identity user risk information for all users in your organization without a signed-in user. | Yes |
| _IdentityRiskyServicePrincipal.Read.All_ |   Read all risky service principal information  | Allows the app to read all risky service principal information for your organization, without a signed-in user. | Yes |
| _IdentityRiskyServicePrincipal.ReadWrite.All_ |   Read and write all risky service principal information  | Allows the app to read and update risky service principal for your organization, without a signed-in user.| Yes |

All identity risk permissions are valid only for work or school accounts. For an app with delegated permissions to read identity risk information, the signed-in user must be a member of one of the following [Azure AD administrator roles](/azure/active-directory/roles/permissions-reference): Global Administrator, Security Administrator, or Security Reader.

### Example usage

The following usages are valid for both delegated and application permissions:

#### Read risk events

* Read all risk events generated for all users in the tenant (`GET /identityProtection/riskDetections`)
* Read most recent 50 risk events (`GET /identityProtection/riskDetections?$orderBy=detectedDateTime desc&top=50`)

#### Read risky users

* Read all risky users and properties in the tenant (`GET /identityProtection/riskyUsers`)
* Read all risky users whose aggregate risk level is Medium (`GET /identityProtection/riskyUsers?$filter=riskLevel eq 'medium'`)
* Read the risk information for a specific user (`GET /identityProtection/riskyUsers?$filter=id eq 'userId'`)

#### Read risky service principals

* Read all risky service principals and properties in the tenant (`GET /identityProtection/riskyServicePrincipals`)
* Read all risky service principals whose aggregate risk level is Medium (`GET /identityProtection/riskyServicePrincipals?$filter=riskLevel eq 'medium'`)
* Read the risk information for a specific service principal (`GET /identityProtection/riskyServicePrincipals?$filter=id eq '{riskyServicePrincipalsId}'`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Identity user flow permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _IdentityUserFlow.Read.All_ |   Read all identity user flows in a tenant  | Allows the app to read your organization's user flows. | Yes | No |
| _IdentityUserFlow.ReadWrite.All_ |   Read and write all identity user flows in a tenant.    | Allows the app to read or write your organization's user flows. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _IdentityUserFlow.Read.All_ |   Read all identity user flows in a tenant  | Allows the app to read your organization's user flows. | Yes | No |
| _IdentityUserFlow.ReadWrite.All_ |   Read and write all identity user flows in a tenant.    | Allows the app to read or write your organization's user flows. | Yes | No |

### Remarks

_IdentityUserFlow.Read.All_ and _IdentityUserFlow.ReadWrite.ALL_ is valid only for work or school accounts.

For an app with delegated permissions to read user flows, the signed-in user must be a member of one of the following administrator roles: Global Administrator, External Identities User Flow Administrator, or Global Reader. For an app with delegated permissions to write user flows, the signed-in user must be a member of one of the following administrator roles: Global Administrator or External Identities User Flow Administrator.

For more information about administrator roles, see [Assigning administrator roles in Azure Active Directory](/azure/active-directory/active-directory-assign-admin-roles).

### Example usage

#### Delegated and Application

The following usages are valid for both delegated and application permissions:

* _IdentityUserFlow.Read.All_: Read all user flows in an Azure AD B2C tenant (`GET beta/identity/b2cUserFlows`)
* _IdentityUserFlow.Read.All_: Read all user flows in an Azure Active Directory (Azure AD) tenant (`GET beta/identity/b2xUserFlows`)
* _IdentityUserFlow.Read.All_: Read all user attribute assignments in an Azure AD B2C user flow (`GET beta/identity/b2cUserFlows/{id}/userAttributeAssignments`)
* _IdentityUserFlow.ReadWrite.All_: Create a new user flow in an Azure AD B2C tenant (`POST beta/identity/b2cUserFlows`)
* _IdentityUserFlow.ReadWrite.All_: Create a new user flow in an Azure Active Directory (Azure AD) tenant (`POST beta/identity/b2xUserflows`)
* _IdentitytUserFlow.ReadWrite.All_: Add an identity provider to an Azure AD B2C user flow (`PATCH beta/identity/b2cUserFlows/{id}/identityProviders/$ref`)
* _IdentityUserFlow.ReadWrite.All_: Remove an identity provider from an Azure AD B2C user flow (`DELETE beta/identity/b2cUserFlows/{id}/identityProviders/{id}`)
* _IdentityUserFlow.ReadWrite.All_: Create a user attribute assignment in an Azure AD B2C user flow (`POST beta/identity/b2cUserFlows/{id}/userAttributeAssignments`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Incidents permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _SecurityIncident.Read.All_ | Read incidents | Allows the app to read incidents, on behalf of the signed-in user. | Yes | No |
| _SecurityIncident.ReadWrite.All_ | Read and write to incidents | Allows the app to read and write incidents, on behalf of the signed-in user. | Yes | No |


#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _SecurityIncident.Read.All_ | Read all incidents | Allows the app to read all incidents, without a signed-in user. | Yes |
| _SecurityIncident.ReadWrite.All_ | Read and write to all incidents | Allows the app to read and write to all incidents, without a signed-in user. | Yes |

### Remarks

Incidents permissions are valid only on work or school accounts.

### Example usage

#### Delegated

* _SecurityIncident.Read.All_: Read all incidents in an organization that the user is allowed to read (`GET /security/incidents`)
* _SecurityIncident.ReadWrite.All_: Read and write to all incidents in an organization that the user is allowed to read and write (`GET /security/incidents`)

#### Application

* _SecurityIncident.Read.All_: Read all incidents in an organization (`GET /security/incidents`)
* _SecurityIncident.ReadWrite.All_: Read and write to all incidents in an organization (`GET /security/incidents`)

---

## Industry data permissions

#### Delegated permissions

| Permission                                  | Display String                                            | Description                                                                                                   | Admin Consent Required | Microsoft Account supported |
| ------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | :--------------------- | :-------------------------- |
| _IndustryData.ReadBasic.All_                | Read basic industry data service and resource definitions | Allows the app to read basic industry data service and resource information on behalf of the signed-in user. | No                     | No                          |
| _IndustryData-DataConnector.Read.All_       | View data connector definitions                           | Allows the app to read data connectors on behalf of the signed-in user.                           | Yes                    | No                          |
| _IndustryData-DataConnector.ReadWrite.All_  | Manage data connector definitions                         | Allows the app to read and write data connectors on behalf of the signed-in user.                 | Yes                    | No                          |
| _IndustryData-DataConnector.Upload_     | Upload files to a data connector                          | Allows the app to upload data files to a data connector on behalf of the signed-in user.                          | Yes                    | No                          |
| _IndustryData-InboundFlow.Read.All_         | View inbound flow definitions                             | Allows the app to read inbound data flows on behalf of the signed-in user.                             | Yes                    | No                          |
| _IndustryData-InboundFlow.ReadWrite.All_    | Manage inbound flow definitions                           | Allows the app to read and write inbound data flows on behalf of the signed-in user.                   | Yes                    | No                          |
| _IndustryData-ReferenceDefinition.Read.All_ | View reference definitions                                | Allows the app to read reference definitions on behalf of the signed-in user.                                | Yes                    | No                          |
| _IndustryData-Run.Read.All_                 | View current and previous runs                            | Allows the app to read current and previous industry data runs on behalf of the signed-in user.                            | Yes                    | No                          |
| _IndustryData-SourceSystem.Read.All_        | View source system definitions                            | Allows the app to read source system definitions on behalf of the signed-in user.                            | Yes                    | No                          |
| _IndustryData-SourceSystem.ReadWrite.All_   | Manage source system definitions                          | Allows the app to read and write source system definitions on behalf of the signed-in user.                  | Yes                    | No                          |
| _IndustryData-TimePeriod.Read.All_          | Read time period definitions                              | Allows the app to read time period definitions on behalf of the signed-in user.                              | Yes                    | No                          |
| _IndustryData-TimePeriod.ReadWrite.All_     | Manage time period definitions                            | Allows the app to read and write time period definitions on behalf of the signed-in user.                    | Yes                    | No                          |

#### Application permissions

| Permission                                  | Display String                                            | Description                                                                                            | Admin Consent Required |
| ------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | :--------------------- |
| _IndustryData.ReadBasic.All_                | View basic service and resource information               | Allows the app to read basic service and resource information without a signed-in user. | No                     |
| _IndustryData-DataConnector.Read.All_       | View data connector definitions                           | Allows the app to read data connectors without a signed-in user.                           | Yes                    |
| _IndustryData-DataConnector.ReadWrite.All_  | Manage data connector definitions                         | Allows the app to read and write data connectors without a signed-in user.                 | Yes                    |
| _IndustryData-DataConnector.Upload_     | Upload files to a data connector                          | Allows the app to upload data files to a data connector without a signed-in user.                          | Yes                    |
| _IndustryData-InboundFlow.Read.All_         | View inbound flow definitions                             | Allows the app to read inbound data flows without a signed-in user.                             | Yes                    |
| _IndustryData-InboundFlow.ReadWrite.All_    | Manage inbound flow definitions                           | Allows the app to read and write inbound data flows without a signed-in user.                   | Yes                    |
| _IndustryData-ReferenceDefinition.Read.All_ | View reference definitions                                | Allows the app to read reference definitions without a signed-in user.                                | Yes                    |
| _IndustryData-Run.Read.All_                 | View current and previous runs                            | Allows the app to read current and previous industry data runs without a signed-in user.                            | Yes                    |
| _IndustryData-SourceSystem.Read.All_        | View source system definitions                            | Allows the app to read source system definitions without a signed-in user.                            | Yes                    |
| _IndustryData-SourceSystem.ReadWrite.All_   | Manage source system definitions                          | Allows the app to read and write source system definitions without a signed-in user.                  | Yes                    |
| _IndustryData-TimePeriod.Read.All_          | Read time period definitions                              | Allows the app to read time period definitions without a signed-in user.                              | Yes                    |
| _IndustryData-TimePeriod.ReadWrite.All_     | Manage time period definitions                            | Allows the app to read and write time period definitions without a signed-in user.                    | Yes                    |

---

## Information protection policy permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _InformationProtectionPolicy.Read_ |   Read user sensitivity labels and label policies | Allows an app to read information protection sensitivity labels and label policy settings, on behalf of the signed-in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _InformationProtectionPolicy.Read.All_ |   Read all published labels and label policies for an organization | Allows an app to read published sensitivity labels and label policy settings for the entire organization or a specific user, without a signed in user. | Yes |

---


## Intune device management permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_DeviceManagementApps.Read.All_ | Read Microsoft Intune apps | Allows the app to read the properties, group assignments and status of apps, app configurations and app protection policies managed by Microsoft Intune. | Yes | No |
|_DeviceManagementApps.ReadWrite.All_ | Read and write Microsoft Intune apps | Allows the app to read and write the properties, group assignments and status of apps, app configurations and app protection policies managed by Microsoft Intune. | Yes | No |
|_DeviceManagementConfiguration.Read.All_ | Read Microsoft Intune device configuration and policies | Allows the app to read properties of Microsoft Intune-managed device configuration and device compliance policies and their assignment to groups. | Yes | No |
|_DeviceManagementConfiguration.ReadWrite.All_ | Read and write Microsoft Intune device configuration and policies  | Allows the app to read and write properties of Microsoft Intune-managed device configuration and device compliance policies and their assignment to groups. | Yes | No |
|_DeviceManagementManagedDevices.PrivilegedOperations.All_ | Perform user-impacting remote actions on Microsoft Intune devices | Allows the app to perform remote high impact actions such as wiping the device or resetting the passcode on devices managed by Microsoft Intune. | Yes | No |
|_DeviceManagementManagedDevices.Read.All_ | Read Microsoft Intune devices | Allows the app to read the properties of devices managed by Microsoft Intune. | Yes | No |
|_DeviceManagementManagedDevices.ReadWrite.All_ | Read and write Microsoft Intune devices | Allows the app to read and write the properties of devices managed by Microsoft Intune. Does not allow high impact operations such as remote wipe and password reset on the device's owner. | Yes | No |
|_DeviceManagementRBAC.Read.All_ | Read Microsoft Intune RBAC settings | Allows the app to read the properties relating to the Microsoft Intune Role-Based Access Control (RBAC) settings. | Yes | No |
|_DeviceManagementRBAC.ReadWrite.All_ | Read and write Microsoft Intune RBAC settings | Allows the app to read and write the properties relating to the Microsoft Intune Role-Based Access Control (RBAC) settings. | Yes | No |
|_DeviceManagementServiceConfig.Read.All_ | Read Microsoft Intune configuration | Allows the app to read Intune service properties including device enrollment and third party service connection configuration. | Yes | No |
|_DeviceManagementServiceConfig.ReadWrite.All_ | Read and write Microsoft Intune configuration | Allows the app to read and write Microsoft Intune service properties including device enrollment and third party service connection configuration. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_DeviceManagementApps.Read.All_ | Read Microsoft Intune apps | Allows the app to read the properties, group assignments and status of apps, app configurations and app protection policies managed by Microsoft Intune. | Yes | No |
|_DeviceManagementApps.ReadWrite.All_ | Read and write Microsoft Intune apps | Allows the app to read and write the properties, group assignments and status of apps, app configurations and app protection policies managed by Microsoft Intune. | Yes | No |
|_DeviceManagementConfiguration.Read.All_ | Read Microsoft Intune device configuration and policies | Allows the app to read properties of Microsoft Intune-managed device configuration and device compliance policies and their assignment to groups. | Yes | No |
|_DeviceManagementConfiguration.ReadWrite.All_ | Read and write Microsoft Intune device configuration and policies  | Allows the app to read and write properties of Microsoft Intune-managed device configuration and device compliance policies and their assignment to groups. | Yes | No |
|_DeviceManagementManagedDevices.PrivilegedOperations.All_ | Perform user-impacting remote actions on Microsoft Intune devices | Allows the app to perform remote high impact actions such as wiping the device or resetting the passcode on devices managed by Microsoft Intune. | Yes | No |
|_DeviceManagementManagedDevices.Read.All_ | Read Microsoft Intune devices | Allows the app to read the properties of devices managed by Microsoft Intune. | Yes | No |
|_DeviceManagementManagedDevices.ReadWrite.All_ | Read and write Microsoft Intune devices | Allows the app to read and write the properties of devices managed by Microsoft Intune. Does not allow high impact operations such as remote wipe and password reset on the device's owner. | Yes | No |
|_DeviceManagementRBAC.Read.All_ | Read Microsoft Intune RBAC settings | Allows the app to read the properties relating to the Microsoft Intune Role-Based Access Control (RBAC) settings. | Yes | No |
|_DeviceManagementRBAC.ReadWrite.All_ | Read and write Microsoft Intune RBAC settings | Allows the app to read and write the properties relating to the Microsoft Intune Role-Based Access Control (RBAC) settings. | Yes | No |
|_DeviceManagementServiceConfig.Read.All_ | Read Microsoft Intune configuration | Allows the app to read Intune service properties including device enrollment and third party service connection configuration. | Yes | No |
|_DeviceManagementServiceConfig.ReadWrite.All_ | Read and write Microsoft Intune configuration | Allows the app to read and write Microsoft Intune service properties including device enrollment and third party service connection configuration. | Yes | No |

### Remarks

> **Note:** Using the Microsoft Graph APIs to configure Intune controls and policies still requires that the Intune service is [correctly licensed](https://go.microsoft.com/fwlink/?linkid=839381) by the customer.

These permissions are only valid for work or school accounts.

### Example usage

#### Delegated

* _DeviceManagementServiceConfiguration.Read.All_: Check the current state of the Intune subscription (`GET /deviceManagement/subscriptionState`).
* _DeviceManagementServiceConfiguration.ReadWrite.All_: Create new Terms and Conditions (`POST /deviceManagement/termsAndConditions`).
* _DeviceManagementConfiguration.Read.All_: Find the status of a device configuration (`GET /deviceManagement/deviceConfigurations/{id}/deviceStatuses`).
* _DeviceManagementConfiguration.ReadWrite.All_: Assign a device compliance policy to a group (`POST deviceCompliancePolicies/{id}/assign`).
* _DeviceManagementApps.Read.All_: Find all the Windows Store apps published to Intune (`GET /deviceAppManagement/mobileApps?$filter=isOf('microsoft.graph.windowsStoreApp')`).
* _DeviceManagementApps.ReadWrite.All_: Publish a new application (`POST /deviceAppManagement/mobileApps`).
* _DeviceManagementRBAC.Read.All_: Find a role assignment by name (`GET /deviceManagement/roleAssignments?$filter=displayName eq 'My Role Assignment'`).
* _DeviceManagementRBAC.ReadWrite.All_: Create a new custom role (`POST /deviceManagement/roleDefinitions`).
* _DeviceManagementManagedDevices.Read.All_: Find a managed device by name (`GET /managedDevices/?$filter=deviceName eq 'My Device'`).
* _DeviceManagementManagedDevices.ReadWrite.All_: Remove a managed device (`DELETE /managedDevices/{id}`).
* _DeviceManagementManagedDevices.PrivilegedOperations.All_: Reset the passcode on a user's managed device (`POST /managedDevices/{id}/resetPasscode`).

#### Application

* _DeviceManagementServiceConfiguration.Read.All_: Check the current state of the Intune subscription (`GET /deviceManagement/subscriptionState`).
* _DeviceManagementServiceConfiguration.ReadWrite.All_: Create new Terms and Conditions (`POST /deviceManagement/termsAndConditions`).
* _DeviceManagementConfiguration.Read.All_: Find the status of a device configuration (`GET /deviceManagement/deviceConfigurations/{id}/deviceStatuses`).
* _DeviceManagementConfiguration.ReadWrite.All_: Assign a device compliance policy to a group (`POST deviceCompliancePolicies/{id}/assign`).
* _DeviceManagementApps.Read.All_: Find all the Windows Store apps published to Intune (`GET /deviceAppManagement/mobileApps?$filter=isOf('microsoft.graph.windowsStoreApp')`).
* _DeviceManagementApps.ReadWrite.All_: Publish a new application (`POST /deviceAppManagement/mobileApps`).
* _DeviceManagementRBAC.Read.All_: Find a role assignment by name (`GET /deviceManagement/roleAssignments?$filter=displayName eq 'My Role Assignment'`).
* _DeviceManagementRBAC.ReadWrite.All_: Create a new custom role (`POST /deviceManagement/roleDefinitions`).
* _DeviceManagementManagedDevices.Read.All_: Find a managed device by name (`GET /managedDevices/?$filter=deviceName eq 'My Device'`).
* _DeviceManagementManagedDevices.ReadWrite.All_: Remove a managed device (`DELETE /managedDevices/{id}`).
* _DeviceManagementManagedDevices.PrivilegedOperations.All_: Reset the passcode on a user's managed device (`POST /managedDevices/{id}/resetPasscode`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Lifecycle workflows permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _LifecycleWorkflows.Read.All_ |   Read all lifecycle workflows resources | Allows the app to list and read all workflows, tasks and related lifecycle workflows resources on behalf of the signed-in user. | Yes | No |
| _LifecycleWorkflows.ReadWrite.All_ |   Read and write all lifecycle workflows resources | Allows the app to create, update, list, read and delete all workflows, tasks and related lifecycle workflows resources on behalf of the signed-in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _LifecycleWorkflows.Read.All_ |   Read all lifecycle workflows resources  | Allows the app to list and read all workflows, tasks and related lifecycle workflows resources without a signed-in user. | Yes |
| _LifecycleWorkflows.ReadWrite.All_ |   Read and write all lifecycle workflows resources | Allows the app to create, update, list, read and delete all workflows, tasks and related lifecycle workflows resources without a signed-in user. | Yes |

---

## Mail permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Mail.Read_ |    Read user mail | Allows the app to read email in user mailboxes. | No | Yes
| _Mail.ReadBasic_ |    Read user basic mail | Allows the app to read email in the signed-in user's mailbox, except for **body**, **bodyPreview**, **uniqueBody**, **attachments**, **extensions**, and any extended properties. Does not include permissions to search messages. | No | No
| _Mail.ReadWrite_ |    Read and write access to user mail | Allows the app to create, read, update, and delete email in user mailboxes. Does not include permission to send mail.| No | Yes
| _Mail.Read.Shared_ |    Read user and shared mail | Allows the app to read mail that the user can access, including the user's own and shared mail. | No | No
| _Mail.ReadWrite.Shared_ |    Read and write user and shared mail | Allows the app to create, read, update, and delete mail that the user has permission to access, including the user's own and shared mail. Does not include permission to send mail. | No | No
| _Mail.Send_ |    Send mail as a user | Allows the app to send mail as users in the organization. | No | Yes
| _Mail.Send.Shared_ |    Send mail on behalf of others | Allows the app to send mail as the signed-in user, including sending on-behalf of others. | No | No
| _MailboxSettings.Read_ |  Read user mailbox settings | Allows the app to the read user's mailbox settings. Does not include permission to send mail. | No | Yes
| _MailboxSettings.ReadWrite_ |  Read and write user mailbox settings | Allows the app to create, read, update, and delete user's mailbox settings. Does not include permission to directly send mail, but allows the app to create rules that can forward or redirect messages. | No | Yes
| _IMAP.AccessAsUser.All_ | Read and write access to user mail via IMAP | Allows the app to read, update, create and delete email in user mailboxes. Does not include permission to send mail. | No | Yes
| _POP.AccessAsUser.All_ | Read and write access to user mail via POP | Allows the app to read, update, create and delete email in user mailboxes. Does not include permission to send mail. | No | Yes
| _SMTP.Send_ | Send mail as a user using SMTP AUTH | Allows the app to send mail as users in the organization. | No | Yes

#### Application permissions

| Permission                  | Display String                           | Description                                                                                                                                                                        | Admin Consent Required |
|:----------------------------|:-----------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------|
| _Mail.Read_                 | Read mail in all mailboxes               | Allows the app to read mail in all mailboxes without a signed-in user.                                                                                                             | Yes                    |
| _Mail.ReadBasic.All_        | Read all users basic mail                | Allows the app to read all users mailboxes except Body, BodyPreview, UniqueBody, Attachments, ExtendedProperties, and Extensions. Does not include permissions to search messages. | Yes                    |
| _Mail.ReadWrite_            | Read and write mail in all mailboxes     | Allows the app to create, read, update, and delete mail in all mailboxes without a signed-in user. Does not include permission to send mail.                                       | Yes                    |
| _Mail.Send_                 | Send mail as any user                    | Allows the app to send mail as any user without a signed-in user.                                                                                                                  | Yes                    |
| _MailboxSettings.Read_      | Read all user mailbox settings           | Allows the app to read user's mailbox settings without a signed-in user. Does not include permission to send mail.                                                                 | Yes                     |
| _MailboxSettings.ReadWrite_ | Read and write all user mailbox settings | Allows the app to create, read, update, and delete user's mailbox settings without a signed-in user. Does not include permission to send mail.                                     | Yes                    |

> **Important**
Administrators can configure [application access policy](auth-limit-mailbox-access.md) to limit app access to _specific_ mailboxes and not to all the mailboxes in the organization, even if the app has been granted the application permissions of Mail.Read, Mail.ReadWrite, Mail.Send, MailboxSettings.Read, or MailboxSettings.ReadWrite.


### Remarks

_Mail.Read.Shared_, _Mail.ReadWrite.Shared_, and _Mail.Send.Shared_ are only valid for work or school accounts. All other permissions are valid for both Microsoft accounts and work or school accounts.

With the _Mail.Send_ or _Mail.Send.Shared_ permission, an app can send mail and save a copy to the user's Sent Items folder, even if the app does not use a corresponding _Mail.ReadWrite_ or _Mail.ReadWrite.Shared_ permission.

### Example usage

#### Delegated

* _Mail.Read_: List messages in the user's inbox, sorted by `receivedDateTime` (`GET /me/mailfolders/inbox/messages?$orderby=receivedDateTime DESC`).
* _Mail.Read.Shared_: Find all messages with attachments in a user's inbox that has shared their inbox with the signed-in user (`GET /users{id | userPrincipalName}/mailfolders/inbox/messages?$filter=hasAttachments eq true`).
* _Mail.ReadWrite_: Mark a message read (`PATCH /me/messages/{id}`).
* _Mail.Send_: Send a message (`POST /me/sendmail`).
* _MailboxSettings.ReadWrite_: Update the user's automatic reply (`PATCH /me/mailboxSettings`).

#### Application

* _Mail.Read_: Find messages from bob@contoso.com (`GET /users/{id | userPrincipalName}/messages?$filter=from/emailAddress/address eq 'bob@contoso.com'`).
* _Mail.ReadWrite_: Create a new folder in the Inbox named `Expense Reports` (`POST /users/{id | userPrincipalName}/mailfolders`).
* _Mail.Send_: Send a message (`POST /users/{id | userPrincipalName}/sendmail`).
* _MailboxSettings.Read_: Get the default timezone for the user's mailbox (`GET /users/{id | userPrincipalName}/mailboxSettings/timeZone`)


For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Managed tenant permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ManagedTenants.Read.All_ | Read all managed tenant specific information | Allows the app to read all managed tenant information on behalf of the signed-in user. | Yes | No |
| _ManagedTenants.ReadWrite.All_ | Read and write all managed tenant specific information | Allows the app to read and write all managed tenant information on behalf of the signed-in user. | Yes | No |

#### Application permissions

None.

---

## Member permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Member.Read.Hidden_ | Read hidden memberships | Allows the app to read the memberships of hidden groups and administrative units on behalf of the signed-in user, for those hidden groups and administrative units that the signed-in user has access to. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _Member.Read.Hidden_ | Read all hidden memberships | Allows the app to read the memberships of hidden groups and administrative units without a signed-in user. | Yes |

### Remarks
_Member.Read.Hidden_ is valid only on work or school accounts.

Membership in some Microsoft 365 groups can be hidden. This means that only the members of the group can view its members. This feature can be used to help comply with regulations that require an organization to hide group membership from outsiders (for example, a Microsoft 365 group that represents students enrolled in a class).

### Example usage

#### Delegated

* _Member.Read.Hidden_: Read the members of an administrative unit with hidden membership on behalf of the signed-in user (`GET /administrativeUnits/{id}/members`).
* _Member.Read.Hidden_: Read the members of a group with hidden membership on behalf of the signed-in user (`GET /groups/{id}/members`).

#### Application

* _Member.Read.Hidden_: Read the members of an administrative unit with hidden membership (`GET /administrativeUnits/{id}/members`).
* _Member.Read.Hidden_: Read the members of a group with hidden membership (`GET /groups/{id}/members`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Notes permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Notes.Read_ |    Read user OneNote notebooks | Allows the app to read the titles of OneNote notebooks and sections and to create new pages, notebooks, and sections on behalf of the signed-in user. | No | Yes
| _Notes.Create_ |    Create user OneNote notebooks | Allows the app to read the titles of OneNote notebooks and sections and to create new pages, notebooks, and sections on behalf of the signed-in user.| No | Yes
| _Notes.ReadWrite_ |    Read and write user OneNote notebooks | Allows the app to read, share, and modify OneNote notebooks on behalf of the signed-in user. | No | Yes
| _Notes.Read.All_ |    Read all OneNote notebooks that user can access | Allows the app to read OneNote notebooks that the signed-in user has access to in the organization. | No | No
| _Notes.ReadWrite.All_ |    Read and write all OneNote notebooks that user can access | Allows the app to read, share, and modify OneNote notebooks that the signed-in user has access to in the organization.| No | No
| _Notes.ReadWrite.CreatedByApp_ |    Limited notebook access (deprecated) | **Deprecated** <br/>Do not use. No privileges are granted by this permission. | No | No

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _Notes.Read.All_ |    Read all OneNote notebooks | Allows the app to read all the OneNote notebooks in your organization, without a signed-in user. | Yes |
| _Notes.ReadWrite.All_ |    Read and write all OneNote notebooks | Allows the app to read, share, and modify all the OneNote notebooks in your organization, without a signed-in user.| Yes |


### Remarks
_Notes.Read.All_ and _Notes.ReadWrite.All_ are only valid for work or school accounts. All other permissions are valid for both Microsoft accounts and work or school accounts.

With the _Notes.Create_ permission, an app can view the OneNote notebook hierarchy of the signed-in user and create OneNote content (notebooks, section groups, sections, pages, and so on).

_Notes.ReadWrite_ and _Notes.ReadWrite.All_ also allow the app to modify the permissions on the OneNote content that can be accessed by the signed-in user.

For work or school accounts, _Notes.Read.All_ and _Notes.ReadWrite.All_ allow the app to access other users' OneNote content that the signed-in user has permission to within the organization.

### Example usage
#### Delegated

* _Notes.Create_: Create a new notebooks for the signed-in user (`POST /me/onenote/notebooks`).
* _Notes.Read_: Read the notebooks for the signed-in user (`GET /me/onenote/notebooks`).
* _Notes.Read.All_: Get all notebooks that the signed-in user has access to within the organization (`GET /me/onenote/notebooks?includesharednotebooks=true`).
* _Notes.ReadWrite_: Update the page of the signed-in user (`PATCH /me/onenote/pages/{id}/$value`).
* _Notes.ReadWrite.All_: Create a page in another user's notebook that the signed-in user has access to within the organization (`POST /users/{id}/onenote/pages`).

#### Application

* _Notes.Read.All_: Read all users notebooks in a group (`GET /groups/{id}/onenote/notebooks`).
* _Notes.ReadWrite.All_: Update the page in a notebook for any user in the organization (`PATCH /users/{id}/onenote/pages/{id}/$value`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Notifications permissions
#### Delegated permissions
|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Notifications.ReadWrite.CreatedByApp_ | Deliver and manage notifications for this app. | Allow the app to deliver its notifications on behalf of signed-in users. Also allows the app to read, update, and delete the user's notification items for this app. |No |
### Remarks
*Notifications.ReadWrite.CreatedByApp* is valid for both Microsoft accounts and work or school accounts.
The *CreatedByApp* constraint associated with this permission indicates that the service will apply implicit filtering to results based on the identity of the calling app, either the Microsoft account app ID or a set of app IDs configured for a cross-platform application identity.
### Example usage
#### Delegated
* _Notifications.ReadWrite.CreatedByApp_: Publish a user-centric notification, which might then be delivered to the user's multiple application clients running on different endpoints. (POST /me/notifications/).

---

## Online meetings permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_OnlineMeetings.Read_|Read Online Meeting.|Allows an app to read online meeting details on behalf of the signed-in user.|No|No|
|_OnlineMeetings.ReadWrite_|Read and Create Online Meetings.|Allows an app to create, read online meetings on behalf of the signed-in user. |No|No|
|_OnlineMeetingArtifact.Read.All_|Read Online Meeting artifacts.|Allows the app to read online meeting artifacts on behalf of the signed-in user. |No|No|
|_OnlineMeetingTranscript.Read.All_|Read all transcripts of online meetings.|Allows the app to read all transcripts of online meetings on behalf of the signed-in user. |Yes|No|

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
|_OnlineMeetings.Read.All_|Read Online Meeting details from the app |Allows the app to read Online Meeting details in your organization without a signed-in user.|Yes|
|_OnlineMeetings.ReadWrite.All_|Read Online Meeting details from the app|Allows an app to create, read Online Meetings without a signed-in user.|Yes|
|_OnlineMeetingArtifact.Read.All_|Read Online Meeting artifacts from the app |Allows the app to read Online Meeting artifacts in your organization, without a signed-in user.|Yes|
|_OnlineMeetingTranscript.Read.All_|Read all transcripts of online meetings.|Allows the app to read all transcripts of all online meetings, without a signed-in user. |Yes|

> **Important**
Administrators can configure [application access policy](cloud-communication-online-meeting-application-access-policy.md) to allow apps to access online meetings on behalf of a user.

### Example usage

#### Delegated

* _OnlineMeetings.Read_: Retrieve the properties and relationships of an [online meeting](/graph/api/onlinemeeting-get?view=graph-rest-beta&preserve-view=true) (`GET /beta/communications/onlinemeetings/{default id}`).
* _OnlineMeetings.ReadWrite_: Create an [online meeting](/graph/api/application-post-onlinemeetings?view=graph-rest-beta&preserve-view=true) (`POST /beta/communications/onlinemeetings`).

#### Application

* _OnlineMeetings.Read.All_
  * Retrieve the properties and relationships of an [online meeting](/graph/api/onlinemeeting-get?view=graph-rest-beta&preserve-view=true) (`GET /beta/communications/onlinemeetings/?$filter=VideoTeleconferenceId%20eq%20'{id}'`).
  * Retrieve an [online meeting](/graph/api/onlinemeeting-get?view=graph-rest-beta&preserve-view=true) on behalf of a user (`GET /beta/users/{userId}/onlineMeetings/{id})
* _OnlineMeetings.ReadWrite.All_
  * Create an [online meeting](/graph/api/onlinemeeting-get?view=graph-rest-beta&preserve-view=true) on behalf of a user (`POST /beta/users/{userId}/onlineMeetings/)
  * Update an [online meeting](/graph/api/onlinemeeting-get?view=graph-rest-beta&preserve-view=true) on behalf of a user (`PATCH /beta/users/{userId}/onlineMeetings/{id})
  * Delete an [online meeting](/graph/api/onlinemeeting-get?view=graph-rest-beta&preserve-view=true) on behalf of a user (`DELETE /beta/users/{userId}/onlineMeetings/{id})
  
> **Note**: Creating an [online meeting](/graph/api/application-post-onlinemeetings?view=graph-rest-beta&preserve-view=true) creates a meeting on behalf of a user, but does not show it on the user's Calendar.

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## On-premises directory synchronization permissions

### Delegated permissions

| Permission                                   | Display String                                                       | Description                                                                                                                                  | Admin Consent Required | Microsoft Account supported |
| :------------------------------------------- | :------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------- | :-------------------------- |
| OnPremDirectorySynchronization.Read.All      | Read all on-premises directory synchronization information           | Allows the app to read all on-premises directory synchronization information for the organization, on behalf of the signed-in user           | Yes                    | No                          |
| OnPremDirectorySynchronization.ReadWrite.All | Read and write all on-premises directory synchronization information | Allows the app to read and write all on-premises directory synchronization information for the organization, on behalf of the signed-in user | Yes                    | No                          |

### Application permissions

None.
---

## On-premises publishing profiles permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| OnPremisesPublishingProfiles.ReadWrite.All |    Access  On-Premises Publishing Profiles| Allows the app to manage hybrid identity service configuration by creating, viewing, updating and deleting on-premises published resources, on-premises agents and agent groups, on behalf of the signed-in user. | No | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| OnPremisesPublishingProfiles.ReadWrite.All |    Access  On-Premises Publishing Profiles| Allows the app to create, view, update and delete on-premises published resources, on-premises agents and agent groups, as part of a hybrid identity configuration, without a signed in user. | Yes | No |

---

## OpenID Connect (OIDC) scopes

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _email_ |    View users' email address | Allows the app to read your users' primary email address. | No | Yes |
| _offline_access_ |    Access user's data anytime | Allows the app to read and update user data, even when they are not currently using the app.| No | Yes |
| _openid_ |    Sign users in | By using this permission, an app can receive a unique identifier for the user in the form of the sub claim. The permission also gives the app access to the UserInfo endpoint. The openid scope can be used at the Microsoft identity platform token endpoint to acquire ID tokens. The app can use these tokens for authentication.| No | Yes |
| _profile_ |    View users' basic profile | Allows the app to see your users' basic profile (name, picture, user name).| No | Yes |

### Remarks
You can use these scopes to specify artifacts that you want returned in Azure AD authorization and token requests. They are supported differently by the Azure AD v1.0 and v2.0 endpoints.

With the Azure AD v1.0 endpoint, only the _openid_ scope is used. You specify it in the *scope* parameter in an authorization request to return an ID token when you use the OpenID Connect protocol to sign in a user to your app. For more information, see [Authorize access to web applications using OpenID Connect and Azure Active Directory](/azure/active-directory/develop/active-directory-protocols-openid-connect-code). To successfully return an ID token, you must also make sure that the _User.Read_ permission is configured when you register your app.

With the Azure AD v2.0 endpoint, you specify the _offline\_access_ scope in the _scope_ parameter to explicitly request a refresh token when using the OAuth 2.0 or OpenID Connect protocols. With OpenID Connect, you specify the _openid_ scope to request an ID token. You can also specify the _email_ scope, _profile_ scope, or both to return additional claims in the ID token. You do not need to specify the _User.Read_ permission to return an ID token with the v2.0 endpoint. For more information, see [OpenID Connect scopes](/azure/active-directory/develop/active-directory-v2-scopes#openid-connect-scopes).

> [!IMPORTANT]
> 
> The Microsoft Authentication Library (MSAL) currently specifies _offline\_access_, _openid_, _profile_, and _email_ by default in authorization and token requests. This means that, for the default case, if you specify these scopes explicitly, Azure AD may return an error.

---

## Organization permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Organization.Read.All_ |Read organization information | Allows the app to read the organization and related resources, on behalf of the signed-in user. Related resources include things like subscribed SKUs and tenant branding information.|Yes | No |
| _Organization.ReadWrite.All_ |Read and write organization information | Allows the app to read and write the organization and related resources, on behalf of the signed-in user. Related resources include things like subscribed SKUs and tenant branding information. |Yes | No |

<br/>

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Organization.Read.All_ |Read organization information | Allows the app to read the organization and related resources, without a signed-in user. Related resources include things like subscribed SKUs and tenant branding information. | Yes |
| _Organization.ReadWrite.All_ |Read and write organization information | Allows the app to read and write the organization and related resources, without a signed-in user. Related resources include things like subscribed SKUs and tenant branding information. |Yes |


### Example usage

#### Delegated

* _Organization.Read.All_: Get organization information (`GET /organization`).
* _Organization.Read.All_: Get the SKUs that the organization has subscribed to (`GET /subscribedSkus`).

#### Application

* _Organization.ReadWrite.All_: Update organization information (such as **technicalNotificationMails**) (`PATCH /organization/{id}`).

---

## Organizational contact permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _OrgContact.Read.All_ | Read organizational contacts|Allows the app to read all organizational contacts on behalf of the signed-in user. These contacts are managed by the organization and are different from a user's personal contacts.|Yes | No |

<br/>

#### Application permissions

|Permission    |Display String   |Description |Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _OrgContact.Read.All_ |Read organizational contacts | Allows the app to read all organizational contacts without a signed-in user.  These contacts are managed by the organization and are different from a user's personal contacts. | Yes |

### Example usage

#### Delegated

* _OrgContact.Read.All_: Get all organizational contacts (`GET /contacts`).

---

## People permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _People.Read_ |    Read users' relevant people lists | Allows the app to read a scored list of people relevant to the signed-in user. The list can include local contacts, contacts from social networking or your organization's directory, and people from recent communications (such as email and Skype). | No | Yes |
| _People.Read.All_ | Read all users' relevant people lists | Allows the app to read a scored list of people relevant to the signed-in user or other users in the signed-in user's organization. The list can include local contacts, contacts from social networking or your organization's directory, and people from recent communications (such as email and Skype). Also allows the app to search the entire directory of the signed-in user's organization. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _People.Read.All_ | Read all users' relevant people lists | Allows the app to read a scored list of people relevant to the signed-in user or other users in the signed-in user's organization. <br/><br/>The list can include local contacts, contacts from social networking or your organization's directory, and people from recent communications (such as email and Skype). Also allows the app to search the entire directory of the signed-in user's organization. | Yes |

### Remarks

The People.Read.All permission is only valid for work and school accounts.

### Example usage

#### Delegated
* _People.Read_: Read a list of relevant people (`GET /me/people`)
* _People.Read.All_: Read a list of relevant people to another user in the same organization (`GET /users('{id})/people`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Privileged access permissions

#### Delegated permissions

| Permission | Display String | Description | Admin Consent Required | Microsoft Account supported |
|:---------- |:-------------- |:----------- |:---------------------- |:----------------- |
| _PrivilegedAccess.ReadWrite.AzureAD_ |Read and write Privileged Identity Management data for Directory  | Allows the app to have read and write access to Privileged Identity Management APIs for Azure AD. | Yes | No |
| _PrivilegedAccess.ReadWrite.AzureADGroup_ |Read and write Privileged Identity Management data for privileged access groups | Allows the app to have read and write access to Privileged Identity Management APIs for groups. | Yes | No |
| _PrivilegedAccess.ReadWrite.AzureResources_ |Read and write Privileged Identity Management data for Azure Resources | Allows the app to have read and write access to Privileged Identity Management APIs for Azure resources. | Yes | No |

#### Application permissions

| Permission | Display String | Description | Admin Consent Required |
|:---------- |:-------------- |:----------- |:---------------------- |
| _PrivilegedAccess.Read.AzureAD_ |Read Privileged Identity Management data for Directory  | Allows the app to have read access to Privileged Identity Management APIs for Azure AD. | Yes |
| _PrivilegedAccess.Read.AzureADGroup_ |Read Privileged Identity Management data for privileged access groups | Allows the app to have read access to Privileged Identity Management APIs for groups. | Yes |
| _PrivilegedAccess.Read.AzureResources_ |Read Privileged Identity Management data for Azure resources | Allows the app to have read access to Privileged Identity Management APIs for Azure AD resources. | Yes |

---

## Places permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Place.Read.All_ |   Read all company places | Allows the app to read company places (conference rooms and room lists) set up in Exchange Online for the tenant. |Yes | No |
| _Place.ReadWrite.All_ |   Read and write all company places | Allows the app to read and write company places (conference rooms and room lists) set up in Exchange Online for the tenant. |Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Place.Read.All_ |   Read all company places | Allows the app to read company places (conference rooms and room lists) for calendar events and other applications.| Yes |

---

## Policy permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Policy.Read.All_ | Read your organization's policies | Allows the app to read your organization's policies on behalf of the signed-in user. | Yes | No |
| _Policy.Read.PermissionGrant_ | Read consent and permission grant policies | Allows the app to read policies related to consent and permission grants for applications, on behalf of the signed-in user. | Yes | No |
| _Policy.ReadWrite.AccessReview_ |   Read and write your organization's access review policy  | Allows the app to read and write your organization's access review policy on behalf of the signed-in user. | Yes | No |
| _Policy.ReadWrite.ApplicationConfiguration_ | Read and write your organization's application configuration policies | Allows the app to read and write your organization's application configuration policies on behalf of the signed-in user. | Yes | No |
| _Policy.ReadWrite.AuthenticationFlows_ | Read and write your organization's authentication flow policies | Allows the app to read and write the authentication flow policies, on behalf of the signed-in user. | Yes | No |
| _Policy.ReadWrite.AuthenticationMethod_        | Read and write authentication method policies       | Allows the app to read and write the authentication method policies, on behalf of the signed-in user. The signed-in user must also be assigned the Global Administrator role. | Yes | No |
| _Policy.ReadWrite.Authorization_ | Read and write your organization's authorization policy | Allows the app to read and write your organization's authorization policy on behalf of the signed-in user.  For example, authorization policies can control some of the permissions that the out-of-the-box user role has by default. | Yes | No |
| _Policy.ReadWrite.ConditionalAccess_ | Read and write your organization's conditional access policies | Allows the app to read and write your organization's conditional access policies on behalf of the signed-in user. | Yes | No |
| _Policy.ReadWrite.ConsentRequest_ | Read and write your organization's consent requests policy | Allows the app to read and write your organization's consent requests policy on behalf of the signed-in user. | Yes | No |
| _Policy.ReadWrite.CrossTenantAccess_ | Read and write your organization's cross-tenant access policy | Allows the app to read and write your organization's cross-tenant access policy on behalf of the signed-in user. | Yes | No |
| _Policy.ReadWrite.FeatureRollout_ | Read and write your organization's feature rollout policies | Allows the app to read and write your organization's feature rollout policies on behalf of the signed-in user. Includes abilities to assign and remove users and groups to rollout of a specific feature. | Yes | No |
| _Policy.ReadWrite.PermissionGrant_ | Manage consent and permission grant policies | Allows the app to manage policies related to consent and permission grants for applications, on behalf of the signed-in user. | Yes | No |
| _Policy.ReadWrite.TrustFramework_ | Read and write your organization's trust framework policies | Allows the app to read and write your organization's trust framework policies on behalf of the signed-in user. | Yes | No |
| _Policy.ReadWrite.AuthenticationMethod_ | Read and write your organization's authentication method policies | Allows the app to read and write the authentication method policies, on behalf of the signed-in user. | Yes | No |
| _Policy.ReadWrite.MobilityManagement_ | Read and write your organization's mobility management policies. | Allows the app to read and write the mobility management policies on behalf of the signed-in user. These control the settings for mobile device management (MDM) and mobile application management (MAM) applications. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _Policy.Read.All_ | Read your organization's policies | Allows the app to read all your organization's policies without a signed in user. | Yes |
| _Policy.Read.PermissionGrant_ | Read consent and permission grant policies | Allows the app to read policies related to consent and permission grants for applications, without a signed-in user. | Yes |
| _Policy.Read.ApplicationConfiguration_ | Read your organization's application configuration policies | Allows the app to read all your organization's application configuration policies without a signed in user. | Yes |
| _Policy.ReadWrite.AccessReview_ | Read and write your organization's access review policy | Allows the app to read and write your organization's access review policy, without a signed-in user. | Yes |
| _Policy.ReadWrite.ApplicationConfiguration_ | Read and write your organization's application configuration policies | Allows the app to read and write your organization's application configuration policies, without a signed-in user. | Yes |
| _Policy.ReadWrite.AuthenticationFlows_ | Read and write your organization's authentication flow policies | Allows the app to read and write the authentication flow policies for the tenant, without a signed in user. | Yes |
| _Policy.ReadWrite.Authorization_ | Read and write your organization's authorization policy | Allows the app to read and write your organization's authorization policy on behalf of the signed-in user.  For example, authorization policies can control some of the permissions that the out-of-the-box user role has by default. | Yes |
| _Policy.ReadWrite.ConsentRequest_ | Read and write your organization's consent requests policy | Allows the app to read and write your organization's consent requests policy without a signed-in user. | Yes |
| _Policy.ReadWrite.CrossTenantAccess_ | Read and write your organization's cross-tenant access policy | Allows the app to read and write your organization's cross-tenant access policy without a signed-in user. | Yes |
| _Policy.ReadWrite.AuthenticationMethod_   | Read and write all authentication method policies    | Allows the app to read and write all authentication method policies for the tenant, without a signed-in user. | Yes |
| _Policy.ReadWrite.FeatureRollout_ | Read and write feature rollout policies | Allows the app to read and write feature rollout policies without a signed-in user. Includes abilities to assign and remove users and groups to rollout of a specific feature. | Yes |
| _Policy.ReadWrite.PermissionGrant_ | Manage consent and permission grant policies | Allows the app to manage policies related to consent and permission grants for applications, without a signed-in user. | Yes |
| _Policy.ReadWrite.TrustFramework_ | Read and write your organization's trust framework policies | Allows the app to read and write your organization's trust framework policies without a signed in user. | Yes |

### Example usage

The following usages are valid for both delegated and application permissions:

* _Policy.Read.All_: Read your organization's policies (`GET /policies`)
* _Policy.Read.All_: Read your organization's trust framework policies (`GET /beta/trustFramework/policies`)
* _Policy.Read.All_: Read your organization's feature rollout policies (`GET /beta/directory/featureRolloutPolicies`)
* _Policy.ReadWrite.AccessReview_: Read and write your organization's access review policies (`PATCH /beta/policies/accessReviewPolicy`)
* _Policy.ReadWrite.ApplicationConfiguration_: Read and write your organization's application configuration policies (`POST /beta/policies/tokenLifetimePolicies`)
* _Policy.ReadWrite.AuthenticationFlows_: Read and write your organization's authentication flows policy (`PATCH /beta/policies/authenticationFlowsPolicy`)
* _Policy.ReadWrite.AuthenticationMethod_: Use this permission to manage the settings of the authentication methods policy, including enabling and disabling authentication methods, allowing users and groups to use those methods, and configuring other settings related to the authentication methods that users may register and use in a tenant.
* _Policy.ReadWrite.ConditionalAccess_: Read and write your organization's conditional access policies (`POST /beta/identity/conditionalAccess/policies`)
* _Policy.ReadWrite.CrossTenantAccess_: Read and write your organization's cross tenant access policy (`PATCH /beta/policies/crossTenantAccessPolicy`)
* _Policy.ReadWrite.FeatureRollout_: Read and write your organization's feature rollout policies (`POST /beta/directory/featureRolloutPolicies`)
* _Policy.ReadWrite.TrustFramework_: Read and write your organization's trust framework policies (`POST /beta/trustFramework/policies`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Presence permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Presence.Read_ | Read user's presence information | Allows the app to read presence information on behalf of the signed-in user. Presence information includes activity, availability, status note, calendar out-of-office message, timezone and location. | No |
| _Presence.Read.All_ |   Read presence information of all users in your organization | Allows the app to read presence information of all users in the directory on behalf of the signed-in user. Presence information includes activity, availability, status note, calendar out-of-office message, timezone and location. | No |
| _Presence.ReadWrite_ | Read and write a user's presence information | Allows the app to read the presence information and write activity and availability on behalf of the signed-in user. Presence information includes activity, availability, status note, calendar out-of-office message, timezone and location. | Yes |

#### Application permissions
|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _Presence.ReadWrite.All_ | Read and write presence information for all users | Allows the app to read all presence information and write activity and availability of all users in the directory without a signed-in user. Presence information includes activity, availability, status note, calendar out-of-office message, timezone and location. | Yes |

### Example usage

* _Presence.Read_: If you're signed in, retrieve your own presence information (`GET /me/presence`)
* _Presence.Read.All_: Retrieve the presence information of another user (`GET /users/{id}/presence`)
* _Presence.Read.All_: Retrieve the presence information of multiple users (`POST /communications/getPresencesByUserId`)
* _Presence.ReadWrite_:
  * If you're signed in, set the state of your presence session (`POST /me/presence/setPresence`)
  * If you're signed in, set your own preferred presence (`POST /me/presence/setUserPreferredPresence`)
* _Presence.ReadWrite.All_:
  * Set the state of a user's presence session as an application (`POST /users/{id}/presence/setPresence`)
  * Set the preferred presence of a user as an application (`POST /users/{id}/presence/setUserPreferredPresence`)

---

## Programs and program controls permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ProgramControl.Read.All_ |   Read all programs  | Allows the app to read programs on behalf of the signed-in user. | Yes | No |
| _ProgramControl.ReadWrite.All_ |   Manage all programs  | Allows the app to read and write programs on behalf of the signed-in user. | Yes | No |


#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|
| _ProgramControl.Read.All_ |   Read all programs | Allows the app to read programs without a signed-in user. | Yes |
| _ProgramControl.ReadWrite.All_ |   Manage all programs | Allows the app to read and write programs without a signed-in user. | Yes |

### Remarks

_ProgramControl.Read.All_ and _ProgramControl.ReadWrite.All_ are valid only for work or school accounts.

For an app with delegated permissions to read programs and program controls, the signed-in user must be a member of one of the following administrator roles: Global Administrator, Security Administrator, Security Reader or User Administrator. For an app with delegated permissions to write programs and program controls, the signed-in user must be a member of one of the following administrator roles: Global Administrator or User Administrator.  For more information about administrator roles, see [Assigning administrator roles in Azure Active Directory](/azure/active-directory/active-directory-assign-admin-roles).

## Records management permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_RecordsManagement.Read.All_ |Read Records Management configuration, labels, and policies |Allows the application to read any data from Records Management, such as configuration, labels, and policies on behalf of the signed-in user. |Yes |
|_RecordsManagement.ReadWrite.All_ | Read and write Records Management configuration, labels, and policies | Allow the application to create, update and delete any data from Records Management, such as configuration, labels, and policies on behalf of the signed-in user. |Yes |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
|_RecordsManagement.Read.All_ |Read Records Management configuration, labels and policies |Allows the application to read any data from Records Management, such as configuration, labels, and policies without the signed in user. |Yes |
|_RecordsManagement.ReadWrite.All_ | Read and write Records Management configuration, labels and policies |Allow the application to create, update and delete any data from Records Management, such as configuration, labels, and policies without the signed in user. |Yes |

### Example usage

#### Delegated

* _RecordsManagement.Read.All_: Get the list of labels available to the user from Microsoft Purview Records maangement (`GET /security/labels/retentionLabels`)
* _RecordsManagement.ReadWrite.All_: Create a label in Microsoft Purview Records managment (`POST /security/labels/retentionLabels/`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Reports permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Reports.Read.All_ | Read all usage reports | Allows an app to read all service usage reports on behalf of the signed-in user. Services that provide usage reports include Microsoft 365 and Azure Active Directory. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _Reports.Read.All_ | Read all usage reports | Allows an app to read all service usage reports without a signed-in user. Services that provide usage reports include Microsoft 365 and Azure Active Directory. | Yes |

### Remarks
- Reports permissions are only valid for work or school accounts.
- For delegated permissions to allow apps to read service usage reports on behalf of a user, the tenant administrator must have assigned the user an Azure AD limited administrator role. For more details, see [Authorization for APIs to read Microsoft 365 usage reports](reportroot-authorization.md).

### Example usage

#### Application

* _Reports.Read.All_: Read usage detail report of email apps with period of 7 days (`GET /reports/EmailAppUsage(view='Detail',period='D7')/content`).
* _Reports.Read.All_: Read activity detail report of email with date of '2017-01-01' (`GET /reports/EmailActivity(view='Detail',data='2017-01-01')/content`).
* _Reports.Read.All_: Read Microsoft 365 activations detail report (`GET /reports/Office365Activations(view='Detail')/content`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Role management permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _RoleAssignmentSchedule.Read.Directory_ | Read all active role assignments for your company's directory. | Allows the app to read the active role-based access control (RBAC) assignments for your company's directory, on behalf of the signed-in user. This includes reading directory role templates, and directory roles. | Yes | No |
| _RoleEligibilitySchedule.Read.Directory_ | Read all eligible role assignments for your company's directory. | Allows the app to read the eligible role-based access control (RBAC) assignments for your company's directory, on behalf of the signed-in user. This includes reading directory role templates, and directory roles. | Yes | No |
| _RoleManagement.Read.All_ | Read role management data for all RBAC providers. | Allows the app to read the role-based access control (RBAC) settings for all supported [RBAC providers](/graph/api/resources/rolemanagement?view=graph-rest-beta&preserve-view=true), on behalf of the signed-in user. This includes reading role definitions and role assignments. | Yes | No |
| _RoleManagement.Read.Directory_ | Read role management data for Azure AD. | Allows the app to read the role-based access control (RBAC) settings for your company's directory, on behalf of the signed-in user.  This includes reading directory role templates, directory roles and memberships. | Yes | No |
| _RoleManagementPolicy.Read.Directory_ | Read all policies for privileged role assignments for your company's directory. | Allows the app to read policies for privileged role-based access control (RBAC) assignments for your company's directory, on behalf of the signed-in user. | Yes | No |
| _RoleManagement.Read.Exchange_ | Read Exchange Online RBAC configuration | Allows the app to read the role-based access control (RBAC) settings for your organization's Exchange Online service, on behalf of the signed-in user. This includes reading Exchange management role definitions, role groups, role group membership, role assignments, management scopes, and role assignment policies. | Yes | No |
| _RoleAssignmentSchedule.ReadWrite.Directory_ | Read, update, and delete all active role assignments for your company's directory. | Allows the app to read and manage the active role-based access control (RBAC) assignments for your company's directory, on behalf of the signed-in user. This includes managing active directory role membership, and reading directory role templates, directory roles and active memberships. | Yes | No |
| _RoleEligibilitySchedule.ReadWrite.Directory_ | Read, update, and delete  all eligible role assignments for your company's directory. | Allows the app to read and manage the eligible role-based access control (RBAC) assignments for your company's directory, on behalf of the signed-in user. This includes managing eligible directory role membership, and reading directory role templates, directory roles and eligible memberships. | Yes | No |
| _RoleManagement.ReadWrite.Directory_ | Read and write role management data for Azure AD. | Allows the app to read and manage the role-based access control (RBAC) settings for your company's directory, on behalf of the signed-in user. This includes instantiating directory roles and managing directory role membership, and reading directory role templates, directory roles and memberships. | Yes | No |
| _RoleManagementPolicy.ReadWrite.Directory_ | Read, update, and delete all policies for privileged role assignments for your company's directory. | Allows the app to read, update, and delete policies for privileged role-based access control (RBAC) assignments for your company's directory, on behalf of the signed-in user. | Yes | No |
| _RoleManagement.ReadWrite.Exchange_ | Read and write Exchange Online RBAC configuration | Allows the app to read and manage the role-based access control (RBAC) settings for your organization's Exchange Online service, on behalf of the signed-in user. This includes reading, creating, updating, and deleting Exchange management role definitions, role groups, role group membership, role assignments, management scopes, and role assignment policies. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _RoleManagement.Read.All_ | Read role management data for all RBAC providers. | Allows the app to read the role-based access control (RBAC) settings for all supported [RBAC providers](/graph/api/resources/rolemanagement?view=graph-rest-beta&preserve-view=true), without a signed-in user. This includes reading role definitions and role assignments. | Yes |
| _RoleManagement.Read.Directory_ | Read role management data for Azure AD. | Allows the app to read the role-based access control (RBAC) settings for your company's directory, without a signed-in user.  This includes reading directory role templates, directory roles and memberships. | Yes |
| _RoleManagement.ReadWrite.Directory_ | Read and write role management data for Azure AD. | Allows the app to read and manage the role-based access control (RBAC) settings for your company's directory, without a signed-in user. This includes instantiating directory roles and managing directory role membership, and reading directory role templates, directory roles and memberships. | Yes |


### Remarks

> [!CAUTION]
> Permissions that allow granting authorization, such as _RoleManagement.ReadWrite.Directory_, allow an application to grant itself, other applications, or any user, additional privileges. Use caution when granting any of these permissions.

With the _RoleManagement.Read.Directory_ permission an application can read directoryRoles and directoryRoleTemplates. This includes reading membership information for directory roles.

With the _RoleManagement.ReadWrite.Directory_ permission an application can read and write directoryRoles (directoryRoleTemplates are readonly resources). This includes adding and removing members to and from directory roles.

Role management permissions are only valid for work or school accounts.

### Example usage

- _RoleManagement.Read.Directory_: Read the list of available role templates (`GET /directoryRoleTemplates`)
- _RoleManagement.Read.Directory_: Read the list of activated roles in your directory (`GET /directoryRoles`)
- _RoleManagement.Read.Directory_: Read the list of members for a role (`GET /directoryRoles/<id>/members`)
- _RoleManagement.Read.Directory_: Read the list of administrative unit-scoped members for a role (`GET /directoryRoles/<id>/scopedMembers`)
- _RoleManagement.ReadWrite.Directory_: Activate a directory role from a role template  (`POST /directoryRoles`)
- _RoleManagement.ReadWrite.Directory_: Add a member to a directory role (`POST /directoryRoles/<id>/members`)
- _RoleManagement.ReadWrite.Directory_: Add an administrative unit-scoped member to a directory role (`POST /directoryRoles/<id>/scopedMembers`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Schedule management permissions

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Schedule.ReadWrite.All_ (private preview)| Read and Write Shifts service (Teams) data | Allows an app to read and write schedule, schedule groups, shifts, and associated entities in shifts applications without a signed-in user.| Yes | No |
| _Schedule.Read.All_ (private preview)| Read Shifts service (Teams) data | Allows the app to read schedule, schedule groups, shifts, and associated entities in shifts applications without a signed-in user.  | Yes | No |

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:-----------------------|
| _Schedule.ReadWrite.All_ | Read and Write Shifts service (Teams) data | Allows an app to read and write schedule, schedule groups, shifts, and associated entities in shifts applications on behalf of the signed-in user.| No | No |
| _Schedule.Read.All_ | Read Shifts service (Teams) data | Allows the app to read schedule, schedule groups, shifts, and associated entities in shifts applications on behalf of the signed-in user.  | No | No |
| _WorkforceIntegration.ReadWrite.All_ (private preview)| Read and write workforce integrations | Allows the app to manage workforce integrations, to synchronize data from Microsoft Teams Shifts with an integrated system, on behalf of the signed-in user.  | Yes | No |
| _WorkforceIntegration.Read.All_ (private preview)| Read and write workforce integrations | Allows the app to manage workforce integrations, to synchronize data from Microsoft Teams Shifts with an integrated system, on behalf of the signed-in user.  | Yes | No |

## Search permissions

#### Application permissions
|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ExternalConnection.Read.All_ | Read all external connections | Allows the app to read all external connections without a signed-in user. | Yes | No |
| _ExternalConnection.ReadWrite.All_ | Read and write all external connections | Allows the app to read and write all external connections without a signed-in user. | Yes | No |
| _ExternalConnection.ReadWrite.OwnedBy_ | Read and write external connections and connection settings | Allows the app to read and write external connections and their settings without a signed-in user. The app can only read and write external connections that it is authorized to, or it can create new external connections. | Yes | No |
| _ExternalItem.Read.All_ | Read all external items | Allows the app to read all external items without a signed-in user. | Yes | No |
| _ExternalItem.ReadWrite.All_ | Read and write all external items | Allows the app to read and write all external items without a signed-in user. | Yes | No |
| _ExternalItem.ReadWrite.OwnedBy_ | Read and write external items | Allows the app to read and write external items without a signed-in user. The app can only read external items of the connection that it is authorized to. | Yes | No |

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:-----------------------|
| _Acronym.Read.All_ | Read all acronyms | Allows the app to read all acronyms on behalf of a signed-in user. | No | No |
| _Bookmark.Read.All_ | Read all bookmarks | Allows the app to read all bookmarks on behalf of a signed-in user. | No | No |
| _QnA.Read.All_ | Read all qnas | Allows the app to read all question and answer sets on behalf of a signed-in user. | No | No |
| _ExternalConnection.Read.All_ | Read all external connections | Allows the app to read all external connections on behalf of a signed-in user. | Yes | No |
| _ExternalConnection.ReadWrite.All_ | Read and write all external connections | Allows the app to read and write all external connections on behalf of a signed-in user. | Yes | No |
| _ExternalConnection.ReadWrite.OwnedBy_ | Read and write external connections | Allows the app to read and write external connections on behalf of a signed-in user. The app can only read and write external connections that it is authorized to, or it can create new external connections. | Yes | No |
| _ExternalItem.Read.All_ | Read external data | Allow the app to read external datasets and content on behalf of the signed-in user. | Yes | No |
| _ExternalItem.ReadWrite.All_ | Read and write all external items | Allows the app to read and write all external items on behalf of a signed-in user. | Yes | No |
| _ExternalItem.ReadWrite.OwnedBy_ | Read and write external items | Allows the app to read and write external items on behalf of a signed-in user. The app can only read external items of the connection that it is authorized to. | Yes | No |

### Remarks
Search permissions are only valid for work or school accounts.

This search permission is only applicable to ingested data from the indexing API.

Access to data via search requires the read permission to the item. Ex : _Files.Read.All_ to access files via search.

### Example usage

#### Delegated

* _ExternalItem.Read.All_ :  Access external data from the [search API](/graph/api/resources/search-api-overview) (`POST /search/query`).

---

## Search configuration permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:-----------------------|
| _SearchConfiguration.Read.All_ | Read your organization's search configuration. | Allows the app to read search configuration, on behalf of the signed-in user. | Yes | No |
| _SearchConfiguration.ReadWrite.All_ | Read and write your organization's search configuration. | Allows the app to read and write search configurations, on behalf of the signed-in user. | Yes | No |

#### Application permissions
|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _SearchConfiguration.Read.All_ | Read your organization's search configuration. | Allows the app to read search configurations without a signed-in user. | Yes |
| _SearchConfiguration.ReadWrite.All_ | Read and write your organization's search configuration. | Allows the app to read and write search configurations without a signed-in user. | Yes |


### Remarks
Search configuration permissions are only valid for work or school accounts.

### Example usage

#### Delegated and Application

- _SearchConfiguration.Read.All_: Read the list of all bookmarks created for your tenant (`GET /beta/search/bookmarks`)
- _SearchConfiguration.ReadWrite.All_: Update or read all bookmarks created for your tenant  (`PATCH /beta/search/bookmarks/{id}`)

---

## Security permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _AttackSimulation.Read.All_ |Read attack simulation data of an organization | Allows the app to read attack simulation and training data for an organization for the signed-in user. |  Yes | No |
| _AttackSimulation.ReadWrite.All_ |Read, create, and update attack simulation data of an organization |Allows the app to read, create, and update attack simulation and training data for an organization for the signed-in user. |  Yes | No |
| _SecurityActions.Read.All_        |  Read your organization's security actions | Allows the app to read your organization's security actions on behalf of the signed-in user. | Yes  | No |
| _SecurityActions.ReadWrite.All_   | Read and update your organization's security actions | Allows the app to read or update your organization's security actions on behalf of the signed-in user.  | Yes  | No |
| _SecurityAlert.Read.All_ | Read alerts | Allows the app to read alerts, on behalf of the signed-in user. | Yes | No |
| _SecurityAlert.ReadWrite.All_ | Read and write to alerts | Allows the app to read and write alerts, on behalf of the signed-in user. | Yes | No |
| _SecurityEvents.Read.All_        |  Read your organization's security events | Allows the app to read your organization's security events on behalf of the signed-in user. | Yes  | No |
| _SecurityEvents.ReadWrite.All_   | Read and update your organization's security events | Allows the app to read your organization's security events on behalf of the signed-in user. Also allows the app to update editable properties in security events on behalf of the signed-in user. | Yes  | No |
| _SecurityIncident.Read.All_ | Read incidents | Allows the app to read incidents, on behalf of the signed-in user. | Yes | No |
| _SecurityIncident.ReadWrite.All_ | Read and write to incidents | Allows the app to read and write incidents, on behalf of the signed-in user. | Yes | No |
| _ThreatIndicators.ReadWrite.OwnedBy_   | Manage threat indicators this app creates or owns |Allows the app to create threat indicators, and fully manage those threat indicators (read, update and delete) on behalf of the signed-in user.  | Yes  | No |
| _ThreatIndicators.Read.All_   | Read your organization's threat indicators | Allows the app to read all the threat indicators for your organization, on behalf of the signed-in user.  | Yes  | No |
| _ThreatIndicators.ReadWrite.OwnedBy_   | Manage threat indicators this app creates or owns |Allows the app to create threat indicators, and fully manage those threat indicators (read, update and delete) on behalf of the signed-in user.  | Yes  | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _AttackSimulation.Read.All_ |Read attack simulation data of an organization | Allows the app to read attack simulation and training data for an organization without a signed-in user.|  Yes |
| _AttackSimulation.ReadWrite.All_ |Read, create, and update all attack simulation data of an organization | Allows the app to read, create, and update attack simulation and training data for an organization without a signed-in user.|  Yes |
| _SecurityActions.Read.All_        |  Read and write your organization's security events |Allows the app to create other applications, and fully manage those applications (read, update, update application secrets and delete), without a signed-in user. | Yes  |
| _SecurityActions.ReadWrite.All_   | Create and read your organization's security actions | Allows the app to read or create security actions, without a signed-in user. | Yes  |
| _SecurityAlert.Read.All_ | Read all alerts | Allows the app to read all alerts, without a signed-in user. | Yes |
| _SecurityAlert.ReadWrite.All_ | Read and write to all alerts | Allows the app to read and write to all alerts, without a signed-in user. | Yes |
| _SecurityEvents.Read.All_        |  Read your organization's security events | Allows the app to read your organization's security events. | Yes  |
| _SecurityEvents.ReadWrite.All_   | Read and update your organization's security events | Allows the app to read your organization's security events. Also allows the app to update editable properties in security events. | Yes  |
| _SecurityIncident.Read.All_ | Read all incidents | Allows the app to read all incidents, without a signed-in user. | Yes |
| _SecurityIncident.ReadWrite.All_ | Read and write to all incidents | Allows the app to read and write to all incidents, without a signed-in user. | Yes |
| _ThreatIndicators.ReadWrite.OwnedBy_   | Manage threat indicators this app creates or owns | Allows the app to create threat indicators, and fully manage those threat indicators (read, update and delete), without a signed-in user.  It cannot update any threat indicators it does not own. | Yes  |
| _ThreatIndicators.Read.All_   | Manage threat indicators this app creates or owns | Allows the app to read all the threat indicators for your organization, without a signed-in user. | Yes  |
| _ThreatIndicators.ReadWrite.OwnedBy_   | Manage threat indicators this app creates or owns | Allows the app to create threat indicators, and fully manage those threat indicators (read, update and delete), without a signed-in user.  It cannot update any threat indicators it does not own. | Yes  |

### Remarks

Security permissions are valid only on work or school accounts.

### Example usage

#### Delegated

- _SecurityAlert.Read.All_: Read all alerts in an organization that the user is allowed to read (`GET /security/alerts_v2`).
- _SecurityAlert.ReadWrite.All_: Read and write to all alerts in an organization that the user is allowed to read and write (`GET /security/alerts_v2`).
- _SecurityEvents.Read.All_: Read the list of all security alerts from all licensed security providers available in an organization (`GET /beta/security/alerts`).
- _SecurityEvents.ReadWrite.All_: Update or read security alerts from all licensed security providers available in an organization  (`PATCH /beta/security/alerts/{id}`).


#### Application

- _SecurityAlert.Read.All_: Read all alerts in an organization (`GET /security/alerts_v2`).
- _SecurityAlert.ReadWrite.All_: Read and write to all alerts in an organization (`GET /security/alerts`).
- _SecurityEvents.Read.All_: Read the list of all security alerts from all licensed security providers available in an organization (`GET /beta/security/alerts`).
- _SecurityEvents.ReadWrite.All_: Update or read security alerts from all licensed security providers available in an organization  (`PATCH /beta/security/alerts/{id}`).

---

## Service communications permissions

#### Delegated permissions

|   Permission    |  Display String  | Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ServiceHealth.Read.All_ | Read service health | Allows the app to read your tenant's service health information on behalf of the signed-in user. Health information may include service issues or service health overviews. | Yes | Yes |
| _ServiceMessage.Read.All_ | Read service messages | Allows the app to read your tenant's service announcement messages on behalf of the signed-in user. Messages may include information about new or changed features. | Yes | Yes |
| _ServiceMessageViewpoint.Write_ | Update your user status on service announcement messages | Allows the app to update service announcement messages' user status on behalf of the signed-in user. The message status can be marked as read, archive, or favorite. | Yes | Yes |

#### Application permissions

|   Permission    |  Display String  | Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _ServiceHealth.Read.All_ | Read service health | Allows the app to read your tenant's service health information, without a signed-in user. Health information may include service issues or service health overviews. | Yes |
| _ServiceMessage.Read.All_ | Read service messages | Allows the app to read your tenant's service announcement messages, without a signed-in user. Messages may include information about new or changed features. | Yes |

---

## Short Notes permissions

#### Delegated permissions

|   Permission    |  Display String  | Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ShortNotes.Read_ | Read short notes of the signed-in user | Allows the app to read all the short notes a sign-in user has access to. | No | Yes |
| _ShortNotes.ReadWrite_ | Read, create, edit, and delete short notes of the signed-in user | Allows the app to read, create, edit, and delete short notes of a signed-in user. | No | Yes |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _ShortNotes.Read.All_ | Read all users' short notes | Allows the app to read all the short notes without a signed-in user. | Yes |
| _ShortNotes.ReadWrite.All_ | Read, create, edit, and delete all users' short notes | Allows the app to read, create, edit, and delete all the short notes without a signed-in user. | Yes |

---

## Sites permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Sites.Read.All_        | Read items in all site collections | Allows the app to read documents and list items in all site collections on behalf of the signed-in user. | No  | No |
| _Sites.ReadWrite.All_   | Read and write items in all site collections | Allows the app to edit or delete documents and list items in all site collections on behalf of the signed-in user. | No  | No |
| _Sites.Manage.All_      | Create, edit, and delete items and lists in all site collections | Allows the app to manage and create lists, documents, and list items in all site collections on behalf of the signed-in user. | No | No |
| _Sites.FullControl.All_ | Have full control of all site collections | Allows the app to have full control to SharePoint sites in all site collections on behalf of the signed-in user.  | Yes  | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _Sites.Read.All_        | Read items in all site collections | Allows the app to read documents and list items in all site collections without a signed in user. | Yes |
| _Sites.ReadWrite.All_   | Read and write items in all site collections | Allows the app to create, read, update, and delete documents and list items in all site collections without a signed in user. | Yes |
| _Sites.Manage.All_      | Create, edit, and delete items and lists in all site collections | Allows the app to manage and create lists, documents, and list items in all site collections without a signed-in user.  | Yes  |
| _Sites.FullControl.All_ | Have full control of all site collections | Allows the app to have full control to SharePoint sites in all site collections without a signed-in user.  | Yes  |
| _Sites.Selected_ | Access selected site collections | Allow the application to access a subset of site collections without a signed in user.  The specific site collections and the permissions granted will be configured in SharePoint Online. | Yes  |


### Remarks

Sites permissions are valid only on work or school accounts.
The _Sites.Selected_ application permission is available only in the Microsoft Graph API.

### Example usage

#### Delegated

* _Sites.Read.All_: Read the lists on the SharePoint root site (`GET /v1.0/sites/root/lists`)
* _Sites.ReadWrite.All_: Create new list items in a SharePoint list (`POST /v1.0/sites/root/lists/123/items`)
* _Sites.Manage.All_: Add a new list to a SharePoint site (`POST /v1.0/sites/root/lists`)
* _Sites.FullControl.All_: Complete access to SharePoint sites and lists.

---

## Synchronization permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
Synchronization.Read.All | Read all Azure AD synchronization data | Allows the app to read synchronization data on behalf of the signed-in user. | Yes | No |
Synchronization.ReadWrite.All | Read and write all Azure AD synchronization data | Allows the app to read and write synchronization data on behalf of the signed-in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
Synchronization.Read.All | Read all Azure AD synchronization data | Allows the app to read synchronization data on behalf of the signed-in user. | Yes |
Synchronization.ReadWrite.All | Read and write all Azure AD synchronization data | Allows the app to read and write synchronization data on behalf of the signed-in user. | Yes |

### Example usage

#### Delegated
- _Synchronization.Read.All_: Get the list of subject rights request available to the user (`GET /servicePrincipals/{id}/synchronization/jobs/{jobId}/schema`).
- _Synchronization.ReadWrite.All_: Create a subject rights request (`PUT /servicePrincipals/{id}/synchronization/jobs/{jobId}/schema`).

#### Application
- _Synchronization.Read.All_: Get the list of subject rights request available to the user (`GET /servicePrincipals/{id}/synchronization/jobs/{jobId}/`).
- _Synchronization.ReadWrite.All_: Create a subject rights request (`POST /servicePrincipals/{id}/synchronization/jobs/{jobId}/starta`).


## Subject rights request permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
SubjectRightsRequest.Read.All | Read subject rights requests | Allows the app to read subject rights requests on behalf of the signed-in user. | Yes | No |
SubjectRightsRequest.ReadWrite.All | Read and write subject rights requests | Allows the app to read and write subject rights requests on behalf of the signed-in user. | Yes | No |

#### Application permissions
None.

### Example usage
#### Delegated
- SubjectRightsRequest.Read.All_: Get the list of subject rights request available to the user (`GET /privacy/subjectrightsrequests`).
- _SubjectRightsRequest.ReadWrite.All_: Create a subject rights request (`POST /privacy/subjectrightsrequests`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

## Tasks permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Tasks.Read_ | Read user's tasks and task lists | Allows the app to read the signed-in user's tasks and task lists, including any shared with the user. Doesn't include permission to create, delete, or update anything. | No | Yes |
| _Tasks.Read.Shared_ | Read user and shared tasks (preview) | Allows the app to read tasks a user has permissions to access, including their own and shared tasks. | No | No |
| _Tasks.ReadWrite_ | Create, read, update, and delete user's tasks and task lists | Allows the app to create, read, update, and delete the signed-in user's tasks and task lists, including any shared with the user. | No | Yes |
| _Tasks.ReadWrite.Shared_ | Read and write user and shared tasks (preview) | Allows the app to create, read, update, and delete tasks a user has permissions to, including their own and shared tasks. | No | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _Tasks.Read.All_ | Read all users' tasks and tasklist | Allows the app to read all users' tasks and task lists in your organization, without a signed-in user. | Yes |
| _Tasks.ReadWrite.All_ | Read and write all users' tasks and tasklists | Allows the app to create, read, update and delete all users' tasks and task lists in your organization, without a signed-in user | Yes |


### Remarks
_Tasks_ permissions are used to control access for To Do tasks, Planner tasks, and Outlook tasks(deprecated).

_Shared_ permissions are currently only supported for work or school accounts. Even with _Shared_ permissions, reads and writes may fail if the user who owns the shared content has not granted the accessing user permissions to modify content within the folder.

### Example usage
#### Delegated

* _Tasks.Read_: Get all Planner tasks assigned to the current user (`GET /me/planner/tasks`).
* _Tasks.Read.Shared_: Access tasks in a folder shared to you by another user in your organization (`Get /users{id|userPrincipalName}/outlook/taskfolders/{id}/tasks`).
* _Tasks.ReadWrite_: Create a Planner task (`POST /planner/tasks`).
* _Tasks.ReadWrite.Shared_: Complete a task on behalf of another user (`POST /users/{id | userPrincipalName}/outlook/tasks/id/complete`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

#### Application

* _Tasks.Read.All_: Get all Planner plans in a group (`GET /groups/{id}/planner/plans`)
* _Tasks.ReadWrite.All_: Delete a Planner task (`Delete /planner/tasks/{id}`)

---

## Taxonomy permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TermStore.Read.All_        | Read term store data | Allows app to read various terms, sets, and groups in the term store | Yes  | No |
| _TermStore.ReadWrite.All_   | Read and write all term store data | Allows the app to edit or delete terms, sets, and groups in the term store | Yes  | No |

### Remarks

Taxonomy permissions are valid only on work or school accounts.

### Example usage

#### Delegated

* _TermStore.Read.All_: Read the termstore for the tenant (`GET /termStore`)
* _TermStore.ReadWrite.All_: Create new terms in the termStore (`POST /termStore/sets/123/children`)

---

## Teams permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Team.ReadBasic.All_ | Read the names and descriptions of teams | Read the names and descriptions of teams, on behalf of the signed-in user.  | No | No |
| _Team.Create_  | Create teams | Create teams, on behalf of the signed-in user. | Yes | No |

#### Application permissions 

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Team.ReadBasic.All_ | Get a list of all teams | Get a list of all teams, without a signed-in user.  | Yes | No |
| _Team.Create_  | Create teams | Create teams, without a signed-in user. | Yes | No |
| _Teamwork.Migrate.All_|Manage migration to Microsoft Teams|Creating and managing resources for migration to Microsoft Teams|Yes|Yes|

## Team templates permissions

#### Delegated permissions
|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamTemplates.Read_ | TeamTemplates.Read is "Sign-in and read Teams templates available for this user" | Allows read of the available Teams Templates for the user | No | No |

#### Application permissions
|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamTemplates.Read.All_ | Read all available Teams Templates | Allows read of the available Teams Templates, without signed user    | No | No |

## Team settings permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamSettings.Read.All_ | Read teams' settings | Read this team's settings, on behalf of the signed-in user.  | Yes | No |
| _TeamSettings.ReadWrite.All_ | Read and change teams' settings | Read and change all teams' settings, on behalf of the signed-in user.  | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamSettings.Read.All_ | Read all teams' settings | Read this team's settings, without a signed-in user.  | Yes | No |
| _TeamSettings.ReadWrite.All_ | Read and change all teams' settings. | Read and change all teams' settings, without a signed-in user.  | Yes | No |


## Teams activity permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamsActivity.Read_ | Read user's teamwork activity feed | Allows the app to read the signed-in user's teamwork activity feed.  | No | No |
| _TeamsActivity.Send_ | Send a teamwork activity as the user | Allows the app to create new notifications in users' teamwork activity feeds on behalf of the signed in user. These notifications may not be discoverable or be held or governed by compliance policies. | No | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamsActivity.Read.All_ | Read all users' teamwork activity feed | Allows the app to read all users' teamwork activity feed, without a signed-in user. | Yes | No |
| _TeamsActivity.Send_ | Send a teamwork activity to any user | Allows the app to create new notifications in users' teamwork activity feeds without a signed in user. These notifications may not be discoverable or be held or governed by compliance policies. | Yes | No |

## Teams app permissions (deprecated)

>[!NOTE]
>These permissions are deprecated. Use the equivalent TeamsAppInstallation.\*.All permissions instead.

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamsApp.Read.All_ (**Deprecated**)| Read all installed Teams apps | Allows the app to read the Teams apps that are installed for the signed-in user, and in all teams the user is a member of. Does not give the ability to read application-specific settings. | Yes | No |
| _TeamsApp.ReadWrite.All_ (**Deprecated**)| Manage all Teams apps | Allows the app to read, install, upgrade, and uninstall Teams apps, on behalf of the signed-in user and also for teams the user is a member of. Does not give the ability to read or write application-specific settings. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamsApp.Read.All_ (**Deprecated**)| Read all users' installed Teams apps | Allows the app to read the Teams apps that are installed for any user, without a signed-in user. Does not give the ability to read application-specific settings. | Yes | No |
| _TeamsApp.ReadWrite.All_ (**Deprecated**)| Manage all users' Teams apps  | Allows the app to read, install, upgrade, and uninstall Teams apps for any user, without a signed-in user. Does not give the ability to read or write application-specific settings.   | Yes | No |

## Teams app installation permissions

#### Delegated permissions
|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamsAppInstallation.ReadForUser_  | Read user's installed Teams apps| Allows the app to read the Teams apps that are installed for the signed-in user. Does not give the ability to read application-specific settings.| No | No |
| _TeamsAppInstallation.ReadWriteForUser_ | Manage user's installed Teams apps| Allows the app to read, install, upgrade, and uninstall Teams apps installed for the signed in user. Does not give the ability to read application-specific settings.| Yes | No |
| _TeamsAppInstallation.ReadWriteSelfForUser_ | Allow the app to manage itself in teams| Allows a Teams app to read, install, upgrade, and uninstall itself to teams the signed-in user can access.| No | No |
| _TeamsAppInstallation.ReadForTeam_ | Read installed Teams apps in teams| Allows the app to read the Teams apps that are installed in teams the signed-in user can access. Does not give the ability to read application-specific settings.| Yes | No |
| _TeamsAppInstallation.ReadWriteForTeam_ | Manage installed Teams apps in teams| Allows the app to read, install, upgrade, and uninstall Teams apps in teams the signed-in user can access. Does not give the ability to read application-specific settings.| Yes | No |
| _TeamsAppInstallation.ReadWriteSelfForTeam_ | Allow the app to manage itself in teams| Allows a Teams app to read, install, upgrade, and uninstall itself to teams the signed-in user can access.| Yes | No |
| _TeamsAppInstallation.ReadWriteAndConsentForChat_ | Manage installed Teams apps in chats| Allows a Teams app to read, install, upgrade, and uninstall itself to teams the signed-in user can access.| Yes | No |
| _TeamsAppInstallation.ReadWriteAndConsentForTeam_ | Manage installed Teams apps in teams| Allows a Teams app to read, install, upgrade, and uninstall itself to teams the signed-in user can access.| Yes | No |
| _TeamsAppInstallation.ReadWriteAndConsentSelfForChat_ | Allow the Teams app to manage itself and its permission grants in chats| Allows a Teams app to read, install, upgrade, and uninstall itself to teams the signed-in user can access.| Yes | No |
| _TeamsAppInstallation.ReadWriteAndConsentSelfForTeam_ | Allow the Teams app to manage itself and its permission grants in teams| Allows a Teams app to read, install, upgrade, and uninstall itself to teams the signed-in user can access.| Yes | No |

#### Application permissions
|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _TeamsAppInstallation.ReadForUser.All_ | Read installed Teams apps for all users| Allows the app to read the Teams apps that are installed for any user, without a signed-in user. Does not give the ability to read application-specific settings.| Yes |
| _TeamsAppInstallation.ReadWriteForUser.All_ | Manage Teams apps for all users| Allows the app to read, install, upgrade, and uninstall Teams apps for any user, without a signed-in user. Does not give the ability to read application-specific settings.| Yes |
| _TeamsAppInstallation.ReadWriteSelfForUser.All_  | Allow the app to manage itself for all users| Allows a Teams app to read, install, upgrade, and uninstall itself to any user, without a signed-in user.| Yes |
| _TeamsAppInstallation.ReadForTeam.All_ | Read installed Teams apps for all teams| Allows the app to read the Teams apps that are installed in any team, without a signed-in user. Does not give the ability to read application-specific settings.| Yes |
| _TeamsAppInstallation.ReadWriteForTeam.All_ | Manage Teams apps for all teams| Allows the app to read, install, upgrade, and uninstall Teams apps in any team, without a signed-in user. Does not give the ability to read application-specific settings.| Yes |
| _TeamsAppInstallation.ReadWriteSelfForTeam.All_ | Allow the Teams app to manage itself for all teams| Allows a Teams app to read, install, upgrade, and uninstall itself in any team, without a signed-in user.| Yes |
| _TeamsAppInstallation.ReadWriteAndConsentForChat.All_ | Manage installation and permission grants of Teams apps for all chats| Allows the app to read, install, upgrade, and uninstall Teams apps in any chat, without a signed-in user. Gives the ability to manage permission grants for accessing those specific chats' data.| Yes |
| _TeamsAppInstallation.ReadWriteAndConsentForTeam.All_ | Manage installation and permission grants of Teams apps for all teams| Allows the app to read, install, upgrade, and uninstall Teams apps in any team, without a signed-in user. Gives the ability to manage permission grants for accessing those specific teams' data.| Yes |
| _TeamsAppInstallation.ReadWriteAndConsentSelfForChat.All_ | Allow the Teams app to manage itself and its permission grants for all chats| Allows a Teams app to read, install, upgrade, and uninstall itself for any chat, without a signed-in user, and manage its permission grants for accessing those specific chats' data.| Yes |
| _TeamsAppInstallation.ReadWriteAndConsentSelfForTeam.All_ | Allow the Teams app to manage itself and its permission grants for all teams| Allows a Teams app to read, install, upgrade, and uninstall itself for any team, without a signed-in user, and manage its permission grants for accessing those specific teams' data.| Yes |

## Teams app settings permissions

#### Delegated permissions
|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamworkAppSettings.Read.All_  | Read Teams app settings | Allows the app to read the Teams app settings on behalf of the signed-in user.| No | No |
| _TeamworkAppSettings.ReadWrite.All_ | Read and write Teams app settings | Allows the app to read and write the Teams app settings on behalf of the signed-in user.| Yes | No |

#### Application permissions
|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _TeamworkAppSettings.Read.All_ | Read Teams app settings | Allows the app to read the Teams app settings without a signed-in user.| Yes |
| _TeamworkAppSettings.ReadWrite.All_ | Read and write Teams app settings| Allows the app to read and write the Teams app settings without a signed-in user.| Yes |

## Teams device management permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamworkDevice.Read.All_ | Read Teams devices. | Allows the app to read the management data for Teams devices on behalf of the signed-in user.  | Yes | No |
| _TeamworkDevice.ReadWrite.All_ | Read and write Teams devices. | Allows the app to read and write the management data for Teams devices on behalf of the signed-in user.   | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamworkDevice.Read.All_ | Read Teams devices. | Allows the app to read the management data for Teams devices, without a signed-in user.  | Yes | No |
| _TeamworkDevice.ReadWrite.All_ | Read and write Teams devices. | Allows the app to read and write the management data for Teams devices, without a signed-in user. | Yes | No |

## Team member permissions 

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamMember.Read.All_ | Read the members of teams. | Read the members of teams, on behalf of the signed-in user. | Yes | No |
| _TeamMember.ReadWrite.All_ | Add and remove members from teams. | Add and remove members from teams, on behalf of the signed-in user. Also allows changing a member's role, for example from owner to non-owner. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamMember.Read.All_ | Read the members of all teams. | Read the members of all teams, without a signed-in user.  | Yes | No |
| _TeamMember.ReadWrite.All_ | Add and remove members from all teams. | Add and remove members from all teams, without a signed-in user. Also allows changing a team member's role, for example from owner to non-owner. | Yes | No |

## Team resource-specific consent permissions

#### Application permissions

| Permission | Display String | Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamSettings.Read.Group_ | Read this team's settings. | Read this team's settings, without a signed-in user. |No | No |
| _TeamSettings.ReadWrite.Group_ | Update the settings for this team. | Read and write this team's settings, without a signed-in user. |No | No |
| _ChannelSettings.Read.Group_ | Read the names, descriptions, and settings of this team's channels. | Read this team's channel names, channel descriptions, and channel settings, without a signed-in user. |No | No |
| _ChannelSettings.ReadWrite.Group_ | Update the names, descriptions, and settings of this team's channels.| Update this team's channel names, channel descriptions, and channel settings, without a signed-in user. |No | No |
| _Channel.Create.Group_ | Create channels in this team. | Create channels in this team, without a signed-in user. |No | No |
| _Channel.Delete.Group_ | Delete this team's channels. | Delete this team's channels, without a signed-in user. |No | No |
| _ChannelMessage.Read.Group_ | Read the team's channel messages. | Allows an app to read this team's channel's messages, without a signed-in user. |No | No |
| _TeamsAppInstallation.Read.Group_ | See which apps are installed in this team. | See which apps are installed in this team, without a signed-in user. |No | No |
| _TeamsTab.Read.Group_ | Read this team's tabs. | Read this team's tabs, without a signed-in user. |No | No |
| _TeamsTab.Create.Group_ | Create tabs in this team. | Create tabs in this team, without a signed-in user. |No | No |
| _TeamsTab.ReadWrite.Group_ | Update this team's tabs. | Update this team's tabs, without a signed-in user. |No | No |
| _TeamsTab.Delete.Group_ | Delete this team's tabs. | Delete this team's tabs, without a signed-in user. |No | No |
| _TeamMember.Read.Group_ | Read this team's members. | Read this team's members, without a signed-in user. |No | No |
| _Member.Read.Group_ | Read this group's members.| Read this group's members, without a signed-in user. |No | No |
| _Owner.Read.Group_| Read this group's owners.  | Read this group's owners, without a signed-in user. |No | No |
| _File.Read.Group_| Read this team's files and folders. | **Limited support** <br/> (Preview) Read this team's files and folders, without a signed-in users. | No | No |
| _TeamsActivity.Send.Group_| Send activity feed notifications to users in this team. | Allows the app to create new notifications in the teamwork activity feeds of the users in this team, without a signed-in user. | No | No |

## Teams settings permissions

### Delegated permissions

| Permission | Display String | Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Team.ReadBasic.All_ | Read the names and descriptions of teams| Read the names and  descriptions of teams, on behalf of the signed-in user.|No| No |
| _TeamSettings.Read.All_ | Read teams' settings| Read all teams' settings, on behalf of the signed-in user.|Yes| No |
| _TeamSettings.ReadWrite.All_ | Read and change teams' settings.| Read and change all teams' settings, on behalf of the signed-in user.|Yes| No |

### Application permissions

| Permission | Display String | Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Team.ReadBasic.All_ | Get a list of all teams.| Get a list of all teams, without a signed-in user.|Yes| No |
| _TeamSettings.Read.All_ | Read all teams' settings| Read this team's settings, without a signed-in user.|Yes| No |
| _TeamSettings.ReadWrite.All_ | Read and change all teams' settings| Read and change all teams' settings, without a signed-in user.|Yes | No |

## Teams tab permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamsTab.Read.All_ | Read tabs in Microsoft Teams. | Allows the app to read the Teams apps that are installed for the signed-in user, and in all teams the user is a member of. Does not give the ability to read application-specific settings.  | Yes | No |
| _TeamsTab.ReadWrite.All_ | Read and write tabs in Microsoft Teams. | Allows the app to read, install, upgrade, and uninstall Teams apps, on behalf of the signed-in user and also for teams the user is a member of. Does not give the ability to read or write application-specific settings.   | Yes | No |
| _TeamsTab.Create_ | Create tabs in Microsoft Teams. | Allows the app to create tabs in any team in Microsoft Teams, on behalf of the signed-in user. This does not grant the ability to read, modify or delete tabs after they are created, or give access to the content inside the tabs. | Yes | No |
 _TeamsTab.ReadWriteSelfForChat_ | Allow the Teams app to manage only its own tabs in chats. | Allows a Teams app to read, install, upgrade, and uninstall its own tabs in chats the signed-in user can access. | Yes | No |
 _TeamsTab.ReadWriteSelfForTeam_ | Allow the Teams app to manage only its own tabs in teams. | Allows a Teams app to read, install, upgrade, and uninstall its own tabs to teams the signed-in user can access. | Yes | No |
_TeamsTab.ReadWriteSelfForUser_ | Allow the Teams app to manage only its own tabs for a user. | Allows a Teams app to read, install, upgrade, and uninstall its own tabs for the signed-in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamsTab.Read.All_ | Read tabs in Microsoft Teams. | Read the names and settings of tabs inside any team in Microsoft Teams, without a signed-in user. This does not give access to the content inside the tabs.  | Yes | No |
| _TeamsTab.ReadWrite.All_ | Read and write tabs in Microsoft Teams. | Read and write tabs in any team in Microsoft Teams, without a signed-in user. This does not give access to the content inside the tabs. | Yes | No |
| _TeamsTab.Create_ | Create tabs in Microsoft Teams. | Allows the app to create tabs in any team in Microsoft Teams, without a signed-in user. This does not grant the ability to read, modify or delete tabs after they are created, or give access to the content inside the tabs. | Yes | No |
_TeamsTab.ReadWriteSelfForChat.All_ | Allow the Teams app to manage only its own tabs for all chats. | Allows a Teams app to read, install, upgrade, and uninstall its own tabs for any chat, without a signed-in user. | Yes | No |
 _TeamsTab.ReadWriteSelfForTeam.All_ | Allow the Teams app to manage only its own tabs for all teams. | Allows a Teams app to read, install, upgrade, and uninstall its own tabs for any team, without a signed-in user. | Yes | No |
_TeamsTab.ReadWriteSelfForUser.All_ | Allow the Teams app to manage only its own tabs for all users. | Allows a Teams app to read, install, upgrade, and uninstall its own tabs for any user, without a signed-in user. | Yes | No |

## Teams tag permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamworkTag.ReadWrite_| Read and write tags in Microsoft Teams. | Allows the app to read and write tags in Teams, on behalf of the signed-in user.  | Yes | No |
| _TeamworkTag.Read_ | Read tags in Microsoft Teams. | Allows the app to read tags in Teams, on behalf of the signed-in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _TeamworkTag.ReadWrite.All_| Read and write tags in Microsoft Teams. | Allows the app to read and write tags in Teams without a signed-in user.  | Yes | No |
| _TeamworkTag.Read.All_ | Read tags in Microsoft Teams. | Allows the app to read tags in Teams without a signed-in user | Yes | No |


## Tenant information permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _CrossTenantInformation.ReadBasic.All_ | Read basic information about an external tenant. | Allows the app to read limited information about an external tenant, on behalf of the signed-in user.  | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _CrossTenantInformation.ReadBasic.All_ | Read basic information about an external tenant. | Allows the app to read limited information about an external tenant, without a signed-in user.  | Yes |


## Terms of use permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Agreement.Read.All_ | Read all terms of use agreements | Allows the app to read terms of use agreements on behalf of the signed-in user. | Yes | No |
| _Agreement.ReadWrite.All_ | Read and write all terms of use agreements | Allows the app to read and write terms of use agreements on behalf of the signed-in user. | Yes | No |
| _AgreementAcceptance.Read_ | Read user terms of use acceptance statuses | Allows the app to read terms of use acceptance statuses on behalf of the signed-in user. | Yes | No |
| _AgreementAcceptance.Read.All_ | Read terms of use acceptance statuses that user can access | Allows the app to read terms of use acceptance statuses on behalf of the signed-in user. | Yes | No |

### Remarks

All the permissions above are valid only for work or school accounts.

For an app to read or write all agreements or agreement acceptances with delegated permissions, the signed-in user must be assigned the Global Administrator, Conditional Access Administrator or Security Administrator role. For more information about administrator roles, see [Assigning administrator roles in Azure Active Directory](/azure/active-directory/active-directory-assign-admin-roles).

### Example usage

#### Delegated
The following usages are valid for both delegated permissions:

* _Agreement.Read.All_: Read all terms of use agreements (`GET /beta/agreements`)
* _Agreement.ReadWrite.All_: Read and write all terms of use agreements (`POST /beta/agreements`)
* _AgreementAcceptance.Read_ Read user terms of use acceptance statuses (`GET /beta/me/agreementAcceptances`)

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

---

## Threat assessment permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ThreatAssessment.ReadWrite.All_ | Read and write threat assessment requests | Allows an app to read your organization's threat assessment requests on behalf of the signed-in user. Also allows the app to create new requests to assess threats received by your organization on behalf of the signed-in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _ThreatAssessment.Read.All_ | Read threat assessment requests | Allows an app to read your organization's threat assessment requests, without a signed-in user. | Yes |

### Remarks

Threat assessment permissions are valid only on work or school accounts.

### Example usage

#### Delegated

* _ThreatAssessment.ReadWrite.All_: Read and write threat assessment requests (`POST /informationProtection/threatAssessmentRequests`)

#### Application

* _ThreatAssessment.Read.All_: Read threat assessment requests (`GET /informationProtection/threatAssessmentRequests`)

---

## Threat hunting permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ThreatHunting.Read.All_ | Run hunting queries | Allows the app to run hunting queries, on behalf of the signed-in user. | Yes | No |


#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _ThreatHunting.Read.All_ | Run hunting queries | Allows the app to run hunting queries, without a signed-in user. | Yes |

### Remarks

Threat hunting permissions are valid only on work or school accounts.

### Example usage

#### Delegated

* _ThreatHunting.Read.All_: Run hunting query on behalf of the signed in user (`POST /security/runHuntingQuery`)

#### Application

* _ThreatHunting.Read.All_: Run hunting query (`POST /security/runHuntingQuery`)

---

## Threat intelligence permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _ThreatIntelligence.Read.All_ | Read all threat intelligence information | Allows the app to read threat intelligence information, such as indicators, observations, and articles, on behalf of the signed-in user. | Yes | No |


#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _ThreatIntelligence.Read.All_ | Read all threat intelligence information | Allows the app to read threat intellgence information, such as indicators, observations, and articles, without a signed-in user. | Yes |

### Remarks

Threat intelligence permissions are valid only on work or school accounts.

### Example usage

#### Delegated

_ThreatIntelligence.Read.All_: List threat intelligence articles on behalf of the signed-in user (`GET /security/threatIntelligence/articles`)

#### Application

_ThreatIntelligence.Read.All_: Get host reputation information, without a signed-in user (`GET /security/threatIntelligence/hosts/contoso.com/reputation`)

---

## Universal Print permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _Printer.Create_ | Register printers | Allows the application to create (register) printers on behalf of the signed-in user. | Yes | No |
| _Printer.FullControl.All_ | Register, read, update, and unregister printers | Allows the application to create (register), read, update, and delete (unregister) printers on behalf of the signed-in user. | Yes | No |
| _Printer.Read.All_ | Read printers | Allows the application to read printers on behalf of the signed-in user. | Yes | No |
| _Printer.ReadWrite.All_ | Read and update printers | Allows the application to read and update printers on behalf of the signed-in user. Does not allow creating (registering) or deleting (unregistering) printers. | Yes | No |
| _PrinterShare.ReadBasic.All_ | Read basic information about printer shares | Allows the application to read basic information about printer shares on behalf of the signed-in user. Does not allow reading access control information. | No | No |
| _PrinterShare.Read.All_ | Read printer shares | Allows the application to read printer shares on behalf of the signed-in user. | No | No |
| _PrinterShare.ReadWrite.All_ | Read and write printer shares | Allows the application to read and update printer shares on behalf of the signed-in user. | Yes | No |
| _PrintJob.Create_ | Create print jobs | Allows the application to create print jobs on behalf of the signed-in user and upload document content to print jobs that the signed-in user created. | No | No |
| _PrintJob.Read_ | Read user's print jobs | Allows the application to read the metadata and document content of print jobs that the signed-in user created. | No | No |
| _PrintJob.Read.All_ | Read print jobs | Allows the application to read the metadata and document content of print jobs on behalf of the signed-in user. | Yes | No |
| _PrintJob.ReadBasic_ | Read basic information of user's print jobs | Allows the application to read the metadata of print jobs that the signed-in user created. Does not allow access to print job document content. | No | No |
| _PrintJob.ReadBasic.All_ | Read basic information of print jobs | Allows the application to read the metadata of print jobs on behalf of the signed-in user. Does not allow access to print job document content. | Yes | No |
| _PrintJob.ReadWrite_ | Read and write user's print jobs | Allows the application to read and update the metadata and document content of print jobs that the signed-in user created. | No | No |
| _PrintJob.ReadWrite.All_ | Read and write print jobs | Allows the application to read and update the metadata and document content of print jobs on behalf of the signed-in user. | Yes | No |
| _PrintJob.ReadWriteBasic_ | Read and write basic information of user's print jobs | Allows the application to read and update the metadata of print jobs that the signed-in user created. Does not allow access to print job document content. | No | No |
| _PrintJob.ReadWriteBasic.All_ | Read and write basic information of print jobs | Allows the application to read and update the metadata of print jobs on behalf of the signed-in user. Does not allow access to print job document content. | Yes | No |
| _PrintConnector.Read.All_ | Read connectors | Allows the application to read connectors on behalf of the signed-in user. | Yes | No |
| _PrintConnector.ReadWrite.All_ | Read and write print connectors | Allows the application to read and write print connectors on behalf of the signed-in user. | Yes | No |
| _PrintSettings.Read.All_ | Read tenant-wide print settings | Allows the application to read print settings on behalf of the signed-in user. | Yes | No |
| _PrintSettings.ReadWrite.All_ | Read and write tenant-wide print settings | Allows the application to read and update print settings on behalf of the signed-in user. | Yes | No |

#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _Printer.Read.All_ | Read printers | Allows the application to read printers without a signed-in user. | Yes |
| _Printer.ReadWrite.All_ | Read and update printers | Allows the application to read and update printers without a signed-in user. Does not allow creating (registering) or deleting (unregistering) printers. | Yes |
| _PrintJob.Manage.All_ | Perform advanced operations on print jobs | Allows the application to perform advanced operations like redirecting a print job to another printer without a signed-in user. Also allows the application to read and update the metadata of print jobs. | Yes |
| _PrintJob.Read.All_ | Read print jobs | Allows the application to read the metadata and document content of print jobs without a signed-in user. | Yes |
| _PrintJob.ReadBasic.All_ | Read basic information for print jobs | Allows the application to read the metadata of print jobs without a signed-in user. Does not allow access to print job document content. | Yes |
| _PrintJob.ReadWrite.All_ | Read and write print jobs | Allows the application to read and update the metadata and document content of print jobs without a signed-in user. | Yes |
| _PrintJob.ReadWriteBasic.All_ | Read and write basic information for print jobs | Allows the application to read and update the metadata of print jobs without a signed-in user. Does not allow access to print job document content. | Yes |
| _PrintTaskDefinition.ReadWrite.All_ | Read, write and update print task definitions | Allows the application to read and update print task definitions without a signed-in user. | Yes |

### Remarks

* To use the Universal Print service, the user or app's tenant must have an active Universal Print subscription in addition to the  permissions listed earlier.

* Some permissions distinguish between print job metadata and payload. Metadata describes the configuration of a print job (its name and document configuration, such as whether it should be stapled or printed in color). Payload is the document data itself (the PDF or XPS file to be printed.)

* All PrintJob.* permissions also require at least Printer.Read.All (or a more prviliged permission) because print jobs are stored within printers.

### Example usage

#### Delegated

* _Printer.Read.All_: Get a list of all printers in the tenant (`GET /print/printers`)
* _PrintJob.Read.All_: Get a list of all print jobs queued to a Printer (`GET /print/printers/{id}/jobs`)
* _Printer.FullControl.All_: Delete (unregister) a printer (`DELETE /print/printers/{id}`)
* _PrintJob.ReadWriteBasic.All_: Update metadata (such as current status) of print jobs (`PATCH /print/printers/{id}/jobs/{id}`)
* _PrintJob.ReadWrite.All_: Create print jobs and upload document data to them (`POST /print/printers/{id}/jobs`)

#### Application

* _Printer.Read.All_: Get a list of all printers in the tenant (`GET /print/printers`)

---

## User permissions

#### Delegated permissions

|   Permission    |  Display String   |  Description | Admin Consent Required | Microsoft Account supported |
|:----------------|:------------------|:-------------|:-----------------------|:--------------|
| _User.Read_       |    Sign-in and read user profile | Allows users to sign-in to the app, and allows the app to read the profile of signed-in users. It also allows the app to read basic company information of signed-in users.| No | Yes |
| _User.ReadWrite_ |    Read and write access to user profile | Allows the app to read the signed-in user's full profile. It also allows the app to update the signed-in user's profile information on their behalf. | No | Yes |
| _User.ReadBasic.All_ |    Read all users' basic profiles | Allows the app to read a basic set of profile properties of other users in your organization on behalf of the signed-in user. This includes display name, first and last name, email address, open extensions and photo. Also allows the app to read the full profile of the signed-in user. | No | No |
| _User.Read.All_  |     Read all users' full profiles           | Allows the app to read the full set of profile properties, reports, and managers of other users in your organization, on behalf of the signed-in user. | Yes | No |
| _User.ReadWrite.All_ |     Read and write all users' full profiles | Allows the app to read and write the full set of profile properties, reports, and managers of other users in your organization, on behalf of the signed-in user. Also allows the app to create and delete users as well as reset user passwords on behalf of the signed-in user. | Yes | No |
| _User.Invite.All_  |     Invite guest users to the organization | Allows the app to invite guest users to your organization, on behalf of the signed-in user. | Yes | No |
| _User.EnableDisableAccount.All_       |    Enable and disable user accounts | Allows the app to enable and disable users' accounts, on behalf of the signed-in user.| Yes | No |
| _User.Export.All_       |    Export users' data | Allows the app to export an organizational user's data, when performed by a Company Administrator.| Yes | No |
| _User.ManageIdentities.All_       |    Manage user identities | Allows an application to read, update and delete identities that are associated with a user's account, that the signed-in user has access to. This controls which identities your users can sign-in with. | Yes | No |
| _User-LifeCycleInfo.Read.All_       |    Read all users' lifecycle information | Allows the app to read the lifecycle information like employeeLeaveDateTime of users in your organization, on behalf of the signed-in user. | Yes | No |
| _User-LifeCycleInfo.ReadWrite.All_       |    Read and write all users' lifecycle information | Allows the app to read and write the lifecycle information like employeeLeaveDateTime of users in your organization, on behalf of the signed-in user. | Yes | No |


#### Application permissions

|   Permission    |  Display String   |  Description | Admin Consent Required |
|:----------------|:------------------|:-------------|:-----------------------|
| _User.Read.All_ |    Read all users' full profiles | Allows the app to read the full set of profile properties, group membership, reports and managers of other users in your organization, without a signed-in user.| Yes |
| _User.ReadWrite.All_ |   Read and write all users' full profiles | Allows the app to read and write the full set of profile properties, group membership, reports and managers of other users in your organization, without a signed-in user.  Also allows the app to create and delete non-administrative users. Does not allow reset of user passwords. | Yes |
| _User.Invite.All_  |     Invite guest users to the organization | Allows the app to invite guest users to your organization, without a signed-in user. | Yes |
| _User.EnableDisableAccount.All_       |    Enable and disable user accounts | Allows the app to enable and disable users' accounts, without a signed-in user.| Yes |
| _User.Export.All_       |    Export users' data | Allows the app to export organizational users' data, without a signed-in user.| Yes |
| _User.ManageIdentities.All_       |    Manage all user identities | Allows an application to read, update and delete identities that are associated with a user's account, without a signed in user. This controls which identities users can sign-in with. |  Yes |
| _User-LifeCycleInfo.Read.All_       |    Read all users' lifecycle information | Allows the app to read the lifecycle information like employeeLeaveDateTime of users in your organization, without a signed-in user. |  Yes |
| _User-LifeCycleInfo.ReadWrite.All_       |    Read and write all users' lifecycle information | Allows the app to read and write the lifecycle information like employeeLeaveDateTime of users in your organization, without a signed-in user. |  Yes |

### Remarks

With the _User.Read_ permission, an app can also read the basic company information of the signed-in user for a work or school account through the [organization](/graph/api/resources/organization) resource. The following properties are available: id, displayName, and verifiedDomains.

For work or school accounts, the full profile includes all of the declared properties of the [User](/graph/api/resources/user) resource. On reads, only a limited number of properties are returned by default. To read properties that are not in the default set, use `$select`. The default properties are:

- displayName
- givenName
- jobTitle
- mail
- mobilePhone
- officeLocation
- preferredLanguage
- surname
- userPrincipalName

 _User.ReadWrite_ and _User.Readwrite.All_ delegated permissions allow the app to update the following profile properties for work or school accounts:

- aboutMe
- birthday
- hireDate
- interests
- mobilePhone
- mySite
- pastProjects
- photo
- preferredName
- responsibilities
- schools
- skills

With the _User.ReadWrite.All_ application permission, the app can update all of the declared properties of work or school accounts except for password.

With the _User.ReadWrite.All_ delegated or application permission, updating another user's **businessPhones**, **mobilePhone** or **otherMails** is only allowed on users who are non-administrators or assigned one of the following roles: Directory Readers, Guest Inviter, Message Center Reader and Reports Reader. For more details, see Helpdesk (Password) Administrator in [Azure AD available roles](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

To read or write direct reports (`directReports`) or the manager (`manager`) of a work or school account, the app must have either _User.Read.All_ (read only) or _User.ReadWrite.All_.

The _User.ReadBasic.All_ permission constrains app access to a limited set of properties known as the basic profile. This is because the full profile might contain sensitive directory information. The basic profile includes only the following properties:

- displayName
- givenName
- id
- mail
- photo
- securityIdentifier
- surname
- userPrincipalName

To read the group memberships of a user (`memberOf`), the app must have either [_Group.Read.All_](#group-permissions) or [_Group.ReadWrite.All_](#group-permissions). However, if the user also has membership in a [directoryRole](/graph/api/resources/directoryrole) or an [administrativeUnit](/graph/api/resources/administrativeunit?view=graph-rest-beta&preserve-view=true), the app will need effective permissions to read those resources too, or Microsoft Graph will return an error. This means the app will also need [Directory permissions](#directory-permissions), and, for delegated permissions, the signed-in user will also need sufficient privileges in the organization to access directory roles and administrative units.

With the _User.ManageIdentities.All_ delegated or application permission, it is possible to update the identities (`identities`) of a user. This includes federated (or social identities) or local identities with email or name-based sign-in names.

### Example usage

#### Delegated

* _User.Read_: Read the full profile for the signed-in user (`GET /me`).
* _User.ReadWrite_: Update the photo of the signed-in user (`PUT /me/photo/$value`).
* _User.ReadBasic.All_: Find all users whose name starts with "David" (`GET /users?$filter=startswith(displayName,'David')`).
* _User.Read.All_: Read a user's manager (`GET /users/{id | userPrincipalName}/manager`).

#### Application

* _User.Read.All_: Read all users and relationships through delta query (`GET /beta/users/delta?$select=displayName,givenName,surname`).
* _User.ReadWrite.All_: Update the photo for any user in the organization (`PUT /users/{id | userPrincipalName}/photo/$value`).

For more complex scenarios involving multiple permissions, see [Permission scenarios](#permission-scenarios).

## User activity permissions

#### Delegated permissions

|Permission    |Display String   |Description |Admin Consent Required | Microsoft Account supported |
|:-----------------------------|:-----------------------------------------|:-----------------|:-----------------|:-----------------|
| _UserActivity.ReadWrite.CreatedByApp_ |Read and write app activity to users' activity feed |Allows the app to read and report the signed-in user's activity in the app. |No | Yes |

#### Application permissions
None.

### Remarks
*UserActivity.ReadWrite.CreatedByApp* is valid for both Microsoft accounts and work or school accounts.

The *CreatedByApp* constraint associated with this permission indicates the service will apply implicit filtering to results based on the identity of the calling app, either the MSA app id or a set of app ids configured for a cross-platform application identity.

### Example usage

#### Delegated
* _UserActivity.ReadWrite.CreatedByApp_: Get a list of recent unique user activities based on associated history items published in the last day. (GET /me/activities/recent).
* _UserActivity.ReadWrite.CreatedByApp_: Publish or update a user activity which may be resumed by the user of the application. (PUT /me/activities/%2Farticle%3F12345).
*  _UserActivity.ReadWrite.CreatedByApp_: Publish or update a history item for a specified user activity in order to represent the period of user engagement. (PUT /me/activities/{id}/historyItems/{id}).
*  _UserActivity.ReadWrite.CreatedByApp_: Delete a user activity in response to user initiated request or to remove invalid data. (DELETE /me/activities/{id}).
*  _UserActivity.ReadWrite.CreatedByApp_: Delete a history item in response to user initiated request or to remove invalid data. (DELETE /me/activities/{id}/historyItems/{id}).

---

## User authentication method permissions

#### Delegated permissions

|Permission                              |Display String                        |Description        |Admin Consent Required | Microsoft Account supported |
|:---------------------------------------|:-------------------------------------|:------------------|:----------------------|:----------------------------|
|_UserAuthenticationMethod.Read_         |Read own authentication methods       |Allows the app to read the signed-in user's authentication methods, including phone numbers and Authenticator app settings. This does not allow the app to see secret information like the signed-in user's passwords, or to sign-in or otherwise use the signed-in user's authentication methods. |Yes|No|
|_UserAuthenticationMethod.Read.All_     |Read users' authentication methods    |Allows the app to read authentication methods of all users in your organization that the signed-in user has access to. Authentication methods include things like a user's phone numbers and Authenticator app settings. This does not allow the app to see secret information like passwords, or to sign-in or otherwise use the authentication methods. |Yes|No|
|_UserAuthenticationMethod.ReadWrite_    |Manage own authentication methods     |Allows the app to read and write the signed-in user's authentication methods, including phone numbers and Authenticator app settings. This does not allow the app to see secret information like the signed-in user's passwords, or to sign-in or otherwise use the signed-in user's authentication methods. |Yes|No|
|_UserAuthenticationMethod.ReadWrite.All_|Manage users' authentication methods  |Allows the app to read and write authentication methods of all users in your organization that the signed-in user has access to. Authentication methods include things like a user's phone numbers and Authenticator app settings. This does not allow the app to see secret information like passwords, or to sign-in or otherwise use the authentication methods. |Yes|No|

#### Application permissions

|Permission                              |Display String                        |Description        |Admin Consent Required |
|:---------------------------------------|:-------------------------------------|:------------------|:----------------------|
|_UserAuthenticationMethod.Read.All_     |Read users' authentication methods    |Allows the app to read authentication methods of all users in your organization, without a signed-in user. Authentication methods include things like a user's phone numbers and Authenticator app settings. This does not allow the app to see secret information like passwords, or to sign-in or otherwise use the authentication methods. |Yes|
|_UserAuthenticationMethod.ReadWrite.All_|Manage users' authentication methods  |Allows the application to read and write authentication methods of all users in your organization, without a signed-in user. Authentication methods include things like a user's phone numbers and Authenticator app settings. This does not allow the app to see secret information like passwords, or to sign-in or otherwise use the authentication methods. |Yes|

### Remarks

User authentication method permissions are used to manage authentication methods on users. With these permissions, a delegated user or application can register new authentication methods on a user, read the authentication methods the user already has registered, update those authentication methods, and remove them from the user.

With these permissions, all authentication methods can be read and managed on a user. This includes methods used for:

* Primary authentication (password, FIDO2, Microsoft Authenticator, and so on)
* Second factor of multi-factor authentication/MFA (phone numbers, Microsoft Authenticator, and so on)
* Self-Service Password Reset/SSPR (email address, and so on)

## Windows updates permissions

#### Delegated permissions

|Permission|Display String|Description|Admin Consent Required|Microsoft Account Supported|
|:---|:---|:---|:---|:---|
|_WindowsUpdates.ReadWrite.All_|Read and write all Windows update deployment settings|Allows the app to read and write all Windows update deployment settings for the organization on behalf of the signed-in user.|Yes|No|

#### Application permissions

|Permission|Display String|Description|Admin Consent Required|
|:---|:---|:---|:---|
|_WindowsUpdates.ReadWrite.All_|Read and write all Windows update deployment settings|Allows the app to read and write all Windows update deployment settings for the organization without a signed-in user.|Yes|

### Remarks

All the permissions above are valid only for work or school accounts.

For an app to read or write all Windows update deployment settings with delegated permissions, the signed-in user must be assigned the Global Administrator, Intune Administrator, or Windows Update Deployment Administrator role. For more information about administrator roles, see [Assigning administrator roles in Azure Active Directory](/azure/active-directory/active-directory-assign-admin-roles).

### Example usage

#### Delegated

* _WindowsUpdates.ReadWrite.All_: Create a deployment (`POST /beta/admin/windows/updates/deployments`).

#### Application

* _WindowsUpdates.ReadWrite.All_: Create a deployment (`POST /beta/admin/windows/updates/deployments`).

## Permission scenarios

This section shows some common scenarios that target [user](/graph/api/resources/user) and [group](/graph/api/resources/group) resources in an organization. The tables show the permissions that an app needs to be able to perform specific operations required by the scenario. Note that in some cases the ability of the app to perform specific operations will depend on whether a permission is an application or delegated permission. In the case of delegated permissions, the app's effective permissions will also depend on the privileges of the signed-in user within the organization. For more information, see  [Delegated permissions, Application permissions, and effective permissions](auth/auth-concepts.md#microsoft-graph-permissions).

### Access scenarios on the User resource

| **App tasks involving User**   |  **Required permissions** | **Permission strings** |
|:-------------------------------|:---------------------|:---------------|
| App wants to read other users' basic information (only display name and picture), for example to show in a people picking experience   | _User.ReadBasic.All_  |  Read all user's basic profiles |
| App wants to read complete user profile for signed in user (see direct reports, and manager, and so on)   | _User.Read_ | Enable sign-in and read user profile|
| App wants to read complete user profile all users   | _User.Read.All_ |  Read all user's full profiles   |
| App wants to read files, mail and calendar information for the signed in user   | _User.Read_, _Files.Read_, _Mail.Read_, _Calendars.Read_ | Enable sign-in and read user profile, Read users' files,  Read user mail,  Read user calendars |
| App wants to read the signed-in user's (my) files and files that other users have shared with the signed-in user (me). | _User.Read_, _Files.Read_, _Sites.Read.All_ | Enable sign-in and read user profile, Read users' files,  Read items in all site collections |
| App wants to read and write complete user profile for signed in user   | _User.ReadWrite_ | Read and write access to user profile |
| App wants to read and write complete user profile all users   | _User.ReadWrite.All_ | Read and write all user's full profiles |
| App wants to read and write files, mail and calendar information for the signed in user   | _User.ReadWrite_, _Files.ReadWrite_, _Mail.ReadWrite_, _Calendars.ReadWrite_  |  Read and write access to user profile,  Read and write access to user profile,  Read and write access to user mail, Have full access to user calendars |
| App wants to submit a data policy operation request to export a user's personal data | _User.Export.All_ | Export a user'a personal data. |


### Access scenarios on the Group resource

| **App tasks involving Group**   |  **Required permissions** |  **Permission strings** |
|:-------------------------------|:---------------------|:---------------|
| App wants to read basic group info (only display name and picture), for example to show in a group picking experience   | _Group.Read.All_  | Read all groups|
| App wants to read all content in all Microsoft 365 groups, including files, conversations.  It also needs to show group memberships, be able to update group memberships, (if owner).  |  _Group.Read.All_ | Read items in all site collections, Read all groups|
| App wants to read and write all content in all Microsoft 365 groups, including files, conversations.  It also needs to show group memberships, be able to update group memberships, (if owner).  |   _Group.ReadWrite.All_, _Sites.ReadWrite.All_ |  Read and write all groups, Edit or delete items in all site collections |
| App wants to discover (find) a Microsoft 365 group. It allows the user to search for a particular group and choose one from the enumerated list to allow the user to join the group.   | _Group.ReadWrite.All_ | Read and write all groups|
| App wants to create a group through AAD Graph |   _Group.ReadWrite.All_ | Read and write all groups|


## All permissions and IDs

[!INCLUDE [permissions-ids](includes/permissions-ids.md)]
