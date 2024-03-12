---
title: "Use the $search query parameter in Microsoft Graph"
description: "Microsoft Graph supports the $search OData query parameter to restrict the results of a request to match a search criterion."
author: "FaithOmbongi"
ms.author: ombongifaith
ms.reviewer: Luca.Spolidoro
ms.localizationpriority: high
ms.prod: "applications"
ms.custom: graphiamtop20, scenarios:getting-started
ms.date: 12/08/2022
---

# Use the $search query parameter

In addition to [other OData query parameters](/graph/query-parameters), Microsoft Graph supports the `$search` query parameter to restrict the results of a request to match a search criterion.

The support for the `$search` query parameter varies by entity, with some, such as Azure AD resources that derive from [directoryObject](/graph/api/resources/directoryobject), supporting `$search` only in [advanced queries](/graph/aad-advanced-queries).

> [!NOTE]
> The `$search` query parameter is currently not available in Azure AD B2C tenants.

## Using $search on message collections

You can search messages based on a value in specific message properties. The results of the search are sorted by the date and time that the message was sent. A `$search` request returns up to 1000 results.

If you do a search on messages and specify only a value without specific message properties, the search is carried out on the default search properties of **from**, **subject**, and **body**.

The following example returns all messages in the signed-in user's Inbox that contains "pizza" in any of the three default search properties:

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "search_my_messages"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/me/messages?$search="pizza"
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/search-my-messages-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/search-my-messages-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/search-my-messages-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/search-my-messages-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/search-my-messages-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/search-my-messages-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

Alternatively, you can search messages by specifying message property names in the following table, that are recognized by the Keyword Query Language (KQL) syntax. These property names correspond to properties defined in the **message** entity of Microsoft Graph. Outlook and other Microsoft 365 applications such as SharePoint support KQL syntax, providing the convenience of a common discovery domain for their data stores.

| Searchable email property | Description                                                                                                                                                             | Example                                                                                                                          |
| :------------------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| **attachment**            | The names of files attached to an email message.                                                                                                                        | [GET][search-att-example] `../me/messages?$search="attachment:api-catalog.md"`                                                   |
| **bcc**                   | The **bcc** field of an email message, specified as an SMTP address, display name, or alias.                                                                            | [GET][search-bcc-example] `../me/messages?$search="bcc:samanthab@contoso.com"&$select=subject,bccRecipients`                     |
| **body**                  | The body of an email message.                                                                                                                                           | [GET][search-body-example] `../me/messages?$search="body:excitement"`                                                            |
| **cc**                    | The **cc** field of an email message, specified as an SMTP address, display name, or alias.                                                                             | [GET][search-cc-example] `../me/messages?$search="cc:danas"&$select=subject,ccRecipients`                                        |
| **from**                  | The sender of an email message, specified as an SMTP address, display name, or alias.                                                                                   | [GET][search-from-example] `../me/messages?$search="from:randiw"&$select=subject,from`                                           |
| **hasAttachment**         | True if an email message contains an attachment that is not an inline attachment, false otherwise.                                                                      | [GET][search-from-example] `../me/messages?$search="hasAttachments:true"`                                                        |
| **importance**            | The importance of an email message, which a sender can specify when sending a message. The possible values are `low`, `medium`, or `high`.                              | [GET][search-imp-example] `../me/messages?$search="importance:high"&$select=subject,importance`                                  |
| **kind**                  | The type of message. The possible values are `contacts`, `docs`, `email`, `faxes`, `im`, `journals`, `meetings`, `notes`, `posts`, `rssfeeds`, `tasks`, or `voicemail`. | [GET][search-kind-example] `../me/messages?$search="kind:voicemail"`                                                             |
| **participants**          | The **from**, **to**, **cc**, and **bcc** fields of an email message, specified as an SMTP address, display name, or alias.                                             | [GET][search-part-example] `../me/messages?$search="participants:danas"`                                                         |
| **received**              | The date that an email message was received by a recipient.                                                                                                             | [GET][search-rcvd-example] `../me/messages?$search="received:07/23/2018"&$select=subject,receivedDateTime`                       |
| **recipients**            | The **to**, **cc**, and **bcc** fields of an email meesage, specified as an SMTP address, display name, or alias.                                                       | [GET][search-rcpts-example] `../me/messages?$search="recipients:randiq"&$select=subject,toRecipients,ccRecipients,bccRecipients` |
| **sent**                  | The date that an email message was sent by the sender.                                                                                                                  | [GET][search-sent-example] `../me/messages?$search="sent:07/23/2018"&$select=subject,sentDateTime`                               |
| **size**                  | The size of an item in bytes.                                                                                                                                           | [GET][search-size-example] `../me/messages?$search="size:1..500000"`                                                             |
| **subject**               | The text in the subject line of an email message. .                                                                                                                     | [GET][search-sbj-example] `../me/messages?$search="subject:has"&$select=subject`                                                 |
| **to**                    | The **to** field of an email message, specified as an SMTP address, display name, or alias.                                                                             | [GET][search-to-example]`.../me/messages?$search="to:randiw"&$select=subject,toRecipients`                                       |

For more information about searchable email properties, KQL syntax, supported operators, and tips on searching, see the following articles:

- [Searchable properties in Exchange](/Exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators#searchable-properties-in-exchange).

- [Keyword Query Language (KQL) syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

- [Message properties and search operators for In-Place eDiscovery in Exchange 2016](/Exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators)

## Using $search on person collections

You can use the Microsoft Graph [People API](/graph/api/resources/person) to retrieve the people who are most relevant to a user. Relevance is determined by the user’s communication and collaboration patterns and business relationships. The People API supports the `$search` query parameter. A `$search` request returns up to 250 results.

Searches on people occur on both the **displayName** and **emailAddress** properties of the [person](/graph/api/resources/person) resource.

The following request does a search for a person named "Irene McGowen" in the **displayName** and **emailAddress** properties in each person in the **people** collection of the signed-in user. Because a person named "Irene McGowan" is relevant to the signed-in user, the information for "Irene McGowan" is returned.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "search_my_people"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/me/people/?$search="Irene McGowen"
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/search-my-people-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/search-my-people-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/search-my-people-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/search-my-people-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/search-my-people-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/search-my-people-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

The following example shows the response.

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "value": [
       {
           "id": "C0BD1BA1-A84E-4796-9C65-F8A0293741D1",
           "displayName": "Irene McGowan",
           "givenName": "Irene",
           "surname": "McGowan",
           "birthday": "",
           "personNotes": "",
           "isFavorite": false,
           "jobTitle": "Auditor",
           "companyName": null,
           "yomiCompany": "",
           "department": "Finance",
           "officeLocation": "12/1110",
           "profession": "",
           "userPrincipalName": "irenem@contoso.onmicrosoft.com",
           "imAddress": "sip:irenem@contoso.onmicrosoft.com",
           "scoredEmailAddresses": [
               {
                   "address": "irenem@contoso.onmicrosoft.com",
                   "relevanceScore": -16.446060612802224
               }
           ],
           "phones": [
               {
                   "type": "Business",
                   "number": "+1 412 555 0109"
               }
           ],
           "postalAddresses": [],
           "websites": [],
           "personType": {
               "class": "Person",
               "subclass": "OrganizationUser"
           }
       }
   ]
}
```

To learn more about the People API, see [Get information about relevant people](./people-insights-overview.md#search-people).  

## Using $search on directory object collections

Azure AD resources and their relationships that derive from [directoryObject](/graph/api/resources/directoryobject) support the `$search` query parameter only in [advanced queries](./aad-advanced-queries.md). The search implementation does **not** support "contains" logic. Instead, it uses a tokenization approach that works by extracting words from the property value and the search string using spaces, numbers, different casing, and symbols as shown in the following examples:

- **Spaces**: `hello world` => `hello`, `world`
- **Different casing**⁽¹⁾: `HelloWorld` or `helloWORLD` => `hello`, `world`
- **Symbols**⁽²⁾: `hello.world` => `hello`, `.`, `world`, `helloworld`
- **Numbers**: `hello123world` => `hello`, `123`, `world`

⁽¹⁾ Currently, tokenization only works when the casing is changing from lowercase to uppercase, so `HELLOworld` is considered a single token: `helloworld`, and `HelloWORld` is two tokens: `hello`, `world`.
⁽²⁾ Tokenization logic also combines words that are separated only by symbols; for example, searching for `helloworld` will find `hello-world` and `hello.world`.

> [!NOTE]
>
> - After tokenization, the tokens are matched independently of the original casing, and they are matched in any order. For example, displayName `李四(David Li)` will match search strings such as `李四(David Li)`, `李四`, `David`, `Li`, `David)`, `(李四`, `Li 李`.
> - The tokenized search support works only on the **displayName** and **description** fields. Any field of String type can be put in `$search`; fields other than **displayName** and **description** default to `$filter` `startswith` behavior.
For example:


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "search_groups"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/groups/?$search="displayName:OneVideo" OR "mail:onevideo"
ConsistencyLevel: eventual
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/search-groups-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/search-groups-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [snippet-not-available](../includes/snippets/snippet-not-available.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [snippet-not-available](../includes/snippets/snippet-not-available.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/search-groups-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/search-groups-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

This looks for all groups with display names that has `one` and `video` tokens, or mail starting with `onevideo`.  

`$search` can be used together with `$filter`:


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "search_filter_groups"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/groups/?$filter=mailEnabled eq true&$search="displayName:OneVideo"
ConsistencyLevel: eventual
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/search-filter-groups-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/search-filter-groups-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/search-filter-groups-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/search-filter-groups-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/search-filter-groups-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/search-filter-groups-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

This looks for all mail-enabled groups with display names that look like "OneVideo".
The results are restricted based on a logical conjunction (an "AND") of the `$filter` and the entire query in the `$search`.

The syntax of search follows these rules:

- Generic format: $search="clause1" \[AND \| OR\] "\[clauseX\]"\.
- Any number of clauses is supported. Parentheses for precedence is also supported.
- The syntax for each clause is: "\<property>:\<text to search>".
- The property name must be specified in the clause. Any property that can be used in `$filter` can also be used inside `$search`. Depending on the property, the search behavior is either "search" or "startsWith" if search is not supported on the property.
- The whole clause must be declared inside double quotes. If it contains double quotes or backslash, it should be escaped with a backslash. All the other special characters must be URL encoded.
- Logical `AND` and `OR` operators must be put outside double quotes and they must be in upper case.

The following table shows some examples.

| Object class | Description                                            | Example                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------ | ------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| User         | Address book display name of the user.                 | [GET](https://developer.microsoft.com/graph/graph-explorer?request=users%3F%24search%3D%22displayName%3AGuthr%22&method=GET&version=v1.0&GraphUrl=https://graph.microsoft.com&headers=W3sibmFtZSI6IkNvbnNpc3RlbmN5TGV2ZWwiLCJ2YWx1ZSI6ImV2ZW50dWFsIn1d) `../users?$search="displayName:Guthr"`                                                                                                                    |
| User         | Address book display name or mail of the user.         | [GET](https://developer.microsoft.com/graph/graph-explorer?request=users%3F%24search%3D%22displayName%3AGuthr%22%20OR%20%22mail%3AGuthr%22&method=GET&version=v1.0&GraphUrl=https://graph.microsoft.com&headers=W3sibmFtZSI6IkNvbnNpc3RlbmN5TGV2ZWwiLCJ2YWx1ZSI6ImV2ZW50dWFsIn1d) `../users?$search="displayName:Guthr" OR "mail:Guthr"`                                                                          |
| Group        | Address book display name or description of the group. | [GET](https://developer.microsoft.com/graph/graph-explorer?request=groups%3F%24search%3D%22description%3AOne%22%20AND%20(%22displayName%3AVideo%22%20OR%20%22displayName%3ADrive%22)&method=GET&version=v1.0&GraphUrl=https://graph.microsoft.com&headers=W3sibmFtZSI6IkNvbnNpc3RlbmN5TGV2ZWwiLCJ2YWx1ZSI6ImV2ZW50dWFsIn1d) `../groups?$search="description:One" AND ("displayName:Video" OR "displayName:Drive"` |
| Group        | Address book display name on a mail-enabled group.     | [GET](https://developer.microsoft.com/graph/graph-explorer?request=groups%3F%24filter%3DmailEnabled%20eq%20true%26%24search%3D%22displayName%3AOneVideo%22&method=GET&version=v1.0&GraphUrl=https://graph.microsoft.com&headers=W3sibmFtZSI6IkNvbnNpc3RlbmN5TGV2ZWwiLCJ2YWx1ZSI6ImV2ZW50dWFsIn1d) `../groups?$filter=mailEnabled eq true&$search="displayName:OneVideo"`                                          |

Both the string inputs you provide in `$search`, as well as the searchable properties, are split up into parts by spaces, different casing, and character types (numbers and special characters).

[search-att-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22attachment%3Aapi-catalog%2Emd%22&method=GET&version=v1.0
[search-bcc-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22bcc%3Asamanthab%40contoso%2Ecom%22%26$select=subject,bccRecipients&method=GET&version=v1.0
[search-body-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22body%3Aexcitement%22&method=GET&version=v1.0
[search-cc-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22cc%3Adanas%22%26$select=subject,ccRecipients&method=GET&version=v1.0
[search-from-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22from%3Arandiw%22%26$select=subject,from&method=GET&version=v1.0
[search-hasatt-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22hasAttachments=true%22&method=GET&version=v1.0
[search-imp-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22importance%3Ahigh%22%26$select=subject,importance&method=GET&version=v1.0
[search-kind-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22kind%3Avoicemail%22&method=GET&version=v1.0
[search-part-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22participants%3Adanas%22&method=GET&version=v1.0

[search-rcvd-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22received%3A07/23/2018%22%26$select=subject,receivedDateTime&method=GET&version=v1.0

[search-rcpts-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22recipients%3Arandiw%22%26$select=subject,toRecipients,ccRecipients,bccRecipients&method=GET&version=v1.0
[search-sent-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22sent%3A07/23/2018%22%26$select=subject,sentDateTime&method=GET&version=v1.0
[search-size-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22size%3A1%2E%2E500000%22&method=GET&version=v1.0

[search-sbj-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22subject%3Ahas%22%26$select=subject&method=GET&version=v1.0
[search-to-example]: https://developer.microsoft.com/graph/graph-explorer?request=me/messages?$search=%22to%3Arandiw%22%26$select=subject,toRecipients&method=GET&version=v1.0

## See also

- [Use query parameters to customize responses](/graph/query-parameters)
- [Advanced query capabilities on Azure AD directory objects](/graph/aad-advanced-queries)
- [Query parameter limitations](known-issues.md#query-parameters)
