---
title: "Update user"
description: "Update the properties of a user object."
author: "jpettere"
ms.localizationpriority: high
ms.prod: "users"
doc_type: apiPageType
---

# Update user

Namespace: microsoft.graph

Update the properties of a [user](../resources/user.md) object. Not all properties can be updated by Member or Guest users with their default permissions without Administrator roles. [Compare member and guest default permissions](/azure/active-directory/fundamentals/users-default-permissions#compare-member-and-guest-default-permissions) to see properties they can manage.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | User.ReadWrite, User.ReadWrite.All, User.ManageIdentities.All, Directory.ReadWrite.All    |
|Delegated (personal Microsoft account) | User.ReadWrite    |
|Application | User.ReadWrite.All, User.ManageIdentities.All, Directory.ReadWrite.All |

>[!NOTE]
> - Updating another user's **businessPhones**, **mobilePhone**, or **otherMails** property is only allowed on users who are non-administrators or assigned one of the following roles: Directory Readers, Guest Inviter, Message Center Reader, and Reports Reader. For more details, see Helpdesk (Password) Administrator in [Azure AD built-in roles](/azure/active-directory/roles/permissions-reference).  This is the case for apps granted either the User.ReadWrite.All or Directory.ReadWrite.All delegated or application permissions. Only a Global Administrator assigned the Directory.AccessAsUser.All permission can update these properties for more privileged administrators.
> - Your personal Microsoft account must be tied to an AAD tenant to update your profile with the User.ReadWrite delegated permission on a personal Microsoft account.
> - Updating the **identities** property requires the User.ManageIdentities.All permission. Also, adding a [B2C local account](../resources/objectidentity.md) to an existing **user** object is not allowed, unless the **user** object already contains a local account identity.

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /users/{id | userPrincipalName}
```

## Request headers
| Header       | Value|
|:-----------|:------|
| Authorization  | Bearer {token}. Required.  |
| Content-Type  | application/json  |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|aboutMe|String|A freeform text entry field for the user to describe themselves.|
|accountEnabled|Boolean| `true` if the account is enabled; otherwise, `false`. This property is required when a user is created. A global administrator assigned the _Directory.AccessAsUser.All_ delegated permission can update the **accountEnabled** status of all administrators in the tenant.|
| ageGroup | [ageGroup](../resources/user.md#agegroup-values) | Sets the age group of the user. Allowed values: `null`, `Minor`, `NotAdult` and `Adult`. Refer to the [legal age group property definitions](../resources/user.md#legal-age-group-property-definitions) for further information. |
|birthday|DateTimeOffset|The birthday of the user. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|businessPhones| String collection | The telephone numbers for the user. NOTE: Although this is a string collection, only one number can be set for this property.|
|city|String|The city in which the user is located.|
| companyName | String | The company name which the user is associated. This property can be useful for describing the company that an external user comes from. The maximum length is 64 characters. |
| consentProvidedForMinor | [consentProvidedForMinor](../resources/user.md#consentprovidedforminor-values) | Sets whether consent has been obtained for minors. Allowed values: `null`, `Granted`, `Denied` and `NotRequired`. Refer to the [legal age group property definitions](../resources/user.md#legal-age-group-property-definitions) for further information. |
|country|String|The country/region in which the user is located; for example, `US` or `UK`.|
|department|String|The name for the department in which the user works.|
|displayName|String|The name displayed in the address book for the user. This is usually the combination of the user's first name, middle initial and last name. This property is required when a user is created and it cannot be cleared during updates. |
| employeeId | String | The employee identifier assigned to the user by the organization. The maximum length is 16 characters. |
| employeeType | String | Captures enterprise worker type. For example, `Employee`, `Contractor`, `Consultant`, or `Vendor`. Returned only on `$select`.|
|givenName|String|The given name (first name) of the user.|
|employeeHireDate|DateTimeOffset|The hire date of the user. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|interests|String collection|A list for the user to describe their interests.|
|jobTitle|String|The user’s job title.|
|mail|String|The SMTP address for the user, for example, `jeff@contoso.onmicrosoft.com`. Changes to this property will also update the user's **proxyAddresses** collection to include the value as a SMTP address. For Azure AD B2C accounts, this property can be updated up to only ten times with unique SMTP addresses. |
|mailNickname|String|The mail alias for the user. This property must be specified when a user is created.|
|mobilePhone|String|The primary cellular telephone number for the user.|
|mySite|String|The URL for the user's personal site.|
|officeLocation|String|The office location in the user's place of business.|
| onPremisesExtensionAttributes | [onPremisesExtensionAttributes](../resources/onpremisesextensionattributes.md) | Contains extensionAttributes 1-15 for the user. Note that the individual extension attributes are neither selectable nor filterable. For an `onPremisesSyncEnabled` user, the source of authority for this set of properties is the on-premises and is read-only and is read-only. These extension attributes are also known as Exchange custom attributes 1-15.|
|onPremisesImmutableId|String|This property is used to associate an on-premises Active Directory user account to their Azure AD user object. This property must be specified when creating a new user account in the Graph if you are using a federated domain for the user’s **userPrincipalName** (UPN) property. **Important:** The **$** and **_** characters cannot be used when specifying this property.                            |
|otherMails|String collection |A list of additional email addresses for the user; for example: `["bob@contoso.com", "Robert@fabrikam.com"]`.|
|passwordPolicies|String|Specifies password policies for the user. This value is an enumeration with one possible value being `DisableStrongPassword`, which allows weaker passwords than the default policy to be specified. `DisablePasswordExpiration` can also be specified. The two may be specified together; for example: `DisablePasswordExpiration, DisableStrongPassword`.|
|passwordProfile|[PasswordProfile](../resources/passwordprofile.md)|Specifies the password profile for the user. The profile contains the user’s password. This property is required when a user is created. The password in the profile must satisfy minimum requirements as specified by the **passwordPolicies** property. By default, a strong password is required. This cannot be used for federated users. <br><br> In delegated access, the calling app must be assigned the *Directory.AccessAsUser.All* delegated permission on behalf of the signed-in user. In application-only access, the calling app must be assigned the *User.ReadWrite.All* application permission and at least the *User Administrator* [Azure AD role](/azure/active-directory/roles/permissions-reference).|
|pastProjects|String collection|A list for the user to enumerate their past projects.|
|postalCode|String|The postal code for the user's postal address. The postal code is specific to the user's country/region. In the United States of America, this attribute contains the ZIP code.|
|preferredLanguage|String|The preferred language for the user. Should follow ISO 639-1 Code; for example `en-US`.|
|responsibilities|String collection|A list for the user to enumerate their responsibilities.|
|schools|String collection|A list for the user to enumerate the schools they have attended.|
|skills|String collection|A list for the user to enumerate their skills.|
|state|String|The state or province in the user's address.|
|streetAddress|String|The street address of the user's place of business.|
|surname|String|The user's surname (family name or last name).|
|usageLocation|String|A two letter country code (ISO standard 3166). Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries.  Examples include: `US`, `JP`, and `GB`. Not nullable.|
|userPrincipalName|String|The user principal name (UPN) of the user. The UPN is an Internet-style login name for the user based on the Internet standard RFC 822. By convention, this should map to the user's email name. The general format is alias@domain, where domain must be present in the tenant's collection of verified domains. The verified domains for the tenant can be accessed from the **verifiedDomains** property of [organization](../resources/organization.md). <br>NOTE: This property cannot contain accent characters. Only the following characters are allowed `A - Z`, `a - z`, `0 - 9`, ` ' . - _ ! # ^ ~`. For the complete list of allowed characters, see [username policies](/azure/active-directory/authentication/concept-sspr-policy#userprincipalname-policies-that-apply-to-all-user-accounts). |
|userType|String|A string value that can be used to classify user types in your directory, such as `Member` and `Guest`.          |

> [!NOTE] 
> - The following properties cannot be updated by an app with only application permissions: **aboutMe**, **birthday**, **employeeHireDate**, **interests**, **mySite**, **pastProjects**, **responsibilities**, **schools**, and **skills**.
> - To update the following properties, you must specify them in their own PATCH request, without including the other properties listed in the table above: **aboutMe**, **birthday**, **interests**, **mySite**, **pastProjects**, **responsibilities**, **schools**, and **skills**.

### Manage extensions and associated data

Use this API to manage the directory, schema, and open extensions and their data for users, as follows:

+ Add, update and store data in the extensions for an existing user
+ For directory and schema extensions, remove any stored data by setting the value of the custom extension property to `null`. For open extensions, use the [Delete open extension](/graph/api/opentypeextension-delete) API.

## Response

If successful, this method returns a `204 No Content` response code.

## Example

### Example 1: Update properties of the signed-in user

#### Request

The following example shows a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "update_user"
}-->
```http
PATCH https://graph.microsoft.com/v1.0/me
Content-type: application/json

{
  "businessPhones": [
    "+1 425 555 0109"
  ],
  "officeLocation": "18/2111"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/update-user-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/update-user-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/update-user-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/update-user-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/update-user-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/update-user-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response
The following example shows the response.
<!-- {
  "blockType": "response"
} -->
```http
HTTP/1.1 204 No Content
```

### Example 2: Update properties of the specified user

#### Request

The following example shows a request.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "update_other_user"
}-->
```http
PATCH https://graph.microsoft.com/v1.0/users/{id}
Content-type: application/json

{
  "businessPhones": [
    "+1 425 555 0109"
  ],
  "officeLocation": "18/2111"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/update-other-user-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/update-other-user-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/update-other-user-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/update-other-user-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/update-other-user-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/update-other-user-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


#### Response

The following example shows the response.
<!-- {
  "blockType": "response"
} -->
```http
HTTP/1.1 204 No Content
```


### Example 3: Update the passwordProfile of a user to reset their password

The following example shows a request to reset the password of another user.

#### Request


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "update_user_passwordProfile"
}-->
```http
PATCH https://graph.microsoft.com/v1.0/users/{id}
Content-type: application/json

{
  "passwordProfile": {
    "forceChangePasswordNextSignIn": false,
    "password": "xWwvJ]6NMw+bWH-d"
  }
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/update-user-passwordprofile-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/update-user-passwordprofile-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/update-user-passwordprofile-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/update-user-passwordprofile-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/update-user-passwordprofile-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/update-user-passwordprofile-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


#### Response
<!-- {
  "blockType": "response"
} -->
```http
HTTP/1.1 204 No Content
```


### Example 4: Add or update the values of a schema extension for a user

You can update or assign a value to a single property or all properties in the extension.

#### Request


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "update_schemaextension"
}-->
```msgraph-interactive
PATCH https://graph.microsoft.com/v1.0/users/4562bcc8-c436-4f95-b7c0-4f8ce89dca5e
Content-type: application/json

{
    "ext55gb1l09_msLearnCourses": {
        "courseType": "Admin"
    }
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/update-schemaextension-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/update-schemaextension-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/update-schemaextension-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/update-schemaextension-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/update-schemaextension-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/update-schemaextension-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


#### Response

<!-- {
  "blockType": "response"
} -->
```http
HTTP/1.1 204 No Content
```

>**Note:** To remove the value of the schema extension from the user object, set the property to `null`. For example:
>
>```http
>PATCH https://graph.microsoft.com/v1.0/users/4562bcc8-c436-4f95-b7c0-4f8ce89dca5e
>Content-type: application/json
>
>{
>    "ext55gb1l09_msLearnCourses": null
>}
>```

## See also

- [Add custom data to resources using extensions](/graph/extensibility-overview)
- [Add custom data to users using open extensions (preview)](/graph/extensibility-open-users)
- [Add custom data to groups using schema extensions (preview)](/graph/extensibility-schema-groups)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update user",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
