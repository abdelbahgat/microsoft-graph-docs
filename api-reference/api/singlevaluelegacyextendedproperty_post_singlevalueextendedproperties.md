# Create single-value extended property

Create one or more single-value extended properties in a new or existing instance of a resource. 

The following user resources are supported:
- [message](../resources/message.md)
- [mailFolder](../resources/mailfolder.md)
- [event](../resources/event.md)
- [calendar](../resources/calendar.md)
- [contact](../resources/contact.md)
- [contactFolder](../resources/contactfolder.md) 

As well as the following group resources:
- group [event](../resources/event.md)
- group [calendar](../resources/calendar.md)
- group [post](../resources/post.md) 


### Prerequisites

One of the following **scopes** is required to execute this API, depending on the resource you're
creating the extended property in:

- _Mail.ReadWrite_
- _Calendars.ReadWrite_
- _Contacts.ReadWrite_
- _Group.ReadWrite.All_
 
### HTTP request
You can create extended properties in a new or existing resource instance.

To create one or more extended properties in a _new_ resource instance, use the same REST request as creating the
instance, and include the properties of the new resource instance _and extended property_ in the request body.
Note that some resources support creation in more than one way. For more information on creating these resource instances,
see the corresponding topics for creating a [message](../resources/message.md), [mailFolder](../api/user_post_mailfolders.md),
[event](../api/user_post_events.md), [calendar](../api/user_post_calendars.md),
[contact](../api/user_post_contacts.md), [contactFolder](../api/user_post_contactfolders.md),
[group event](../api/group_post_events.md), and [group post](../resources/post.md). 
 
The following is the syntax of the requests. 

<!-- { "blockType": "ignored" } -->
```http
POST /me/messages
POST /users/<id|userPrincipalName>/messages
POST /me/mailFolders/<id>/messages

POST /me/mailFolders
POST /users/<id|userPrincipalName>/mailFolders

POST /me/events
POST /users/<id|userPrincipalName>/events

POST /me/calendars
POST /users/<id|userPrincipalName>/calendars

POST /me/contacts
POST /users/<id|userPrincipalName>/contacts

POST /me/contactFolders
POST /users/<id|userPrincipalName>/contactFolders

POST /groups/<id>/events

POST /groups/<id>/threads/<id>/posts/<id>/microsoft.graph.reply
POST /groups/<id>/conversations/<id>/threads/<id>/posts/<id>/microsoft.graph.reply
POST /groups/<id>/threads/<id>/microsoft.graph.reply
POST /groups/<id>/conversations/<id>/threads/<id>/microsoft.graph.reply
POST /groups/<id>/threads
POST /groups/<id>/conversations
```

To create one or more extended properties in an existing resource instance, specify the instance in the
request, and include the extended property in the request body.

**Note** You cannot create an extended property in an existing group post.

<!-- { "blockType": "ignored" } -->
```http
PATCH /me/messages/<id>
PATCH /users/<id|userPrincipalName>/messages/<id>
PATCH /me/mailFolders/<id>/messages/<id>

PATCH /me/mailFolders/<id>
PATCH /users/<id|userPrincipalName>/mailFolders/<id>

PATCH /me/events/<id>
PATCH /users/<id|userPrincipalName>/events/<id>

PATCH /me/calendars/<id>
PATCH /users/<id|userPrincipalName>/calendars/<id>

PATCH /me/contacts/<id>
PATCH /users/<id|userPrincipalName>/contacts/<id>

PATCH /me/contactFolders/<id>
PATCH /users/<id|userPrincipalName>/contactFolders/<id>

PATCH /groups/<id>/events/<id>
```


### Parameters
|**Parameter**|**Type**|**Description**|
|:-----|:-----|:-----|
|_URL parameters_|
|id|string|A unique identifier for an object in the corresponding collection. Required.|


### Request headers
| Name       | Value |
|:---------------|:----------|
| Authorization | Bearer %token%|
| Content-Type | application/json |

### Request body

Provide a JSON body of each [singleValueLegacyExtendedProperty](../resources/singleValueLegacyExtendedProperty.md) object in the 
**singleValueExtendedProperties** collection property of the resource instance.

When creating an extended property in a _new_ resource instance, in addition to the 
new **singleValueExtendedProperties** collection, provide a JSON representation of that resource instance (that is, a [message](../resources/message.md), 
[mailFolder](../resources/mailfolder.md), [event](../resources/event.md), etc.)

### Response

#### Response code
An operation successful in creating an extended property in a new resource instance returns `201 Created`, except in a new group post, 
depending on the method used, the operation can return `200 OK` or `202 Accepted`.

In an existing resource instance, a successful create operation returns `200 OK`. 


#### Response body

When creating an extended property in a new resource instance, the response includes only the new instance but not the new extended property. To see the newly
created extended property, [get the new instance expanded with the extended property](../api/singlevaluelegacyextendedproperty_get.md).

When creating an extended property in a _new_ [group post](../resources/post.md), the response includes only a response code but not the new post nor 
the extended property.

When creating an extended property in a _existing_ resource instance, the 
response body includes the new instance expanded with the [singleValueLegacyExtendedProperty](../resources/singleValueLegacyExtendedProperty.md). 




