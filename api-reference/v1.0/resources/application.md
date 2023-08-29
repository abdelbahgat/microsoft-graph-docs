---
title: "application resource type"
description: "Represents an application."
ms.localizationpriority: high
author: "sureshja"
ms.prod: "applications"
doc_type: resourcePageType
---

# application resource type

Namespace: microsoft.graph

Represents an application. Any application that outsources authentication to Azure Active Directory (Azure AD) must be registered in a directory. Application registration involves telling Azure AD about your application, including the URL where it's located, the URL to send replies after authentication, the URI to identify your application, and more. For more information, see [Basics of Registering an Application in Azure AD](/azure/active-directory/develop/authentication-vs-authorization#basics-of-registering-an-application-in-azure-ad). Inherits from [directoryObject](directoryobject.md).

This resource is an open type that allows other properties to be passed in.

This resource supports:

- Adding your own data to custom properties as [extensions](/graph/extensibility-overview).
- Using [delta query](/graph/delta-query-overview) to track incremental additions, deletions, and updates, by providing a [delta](../api/user-delta.md) function.

## Methods

| Method | Return Type | Description |
|:---------------|:--------|:----------|
|[List applications](../api/application-list.md) | [application](application.md) collection | Retrieve the list of applications in the organization. |
|[Create application](../api/application-post-applications.md) | [application](application.md) | Creates (registers) a new application.|
|[Get application](../api/application-get.md) | [application](application.md) |Read properties and relationships of application object.|
|[Update application](../api/application-update.md) | None |Update application object. |
|[Delete application](../api/application-delete.md) | None |Delete application object. |
|[Get delta](../api/application-delta.md)|[application](application.md)|Get newly created, updated, or deleted applications without performing a full read of the entire resource collection.|
|[List deleted applications](../api/directory-deleteditems-list.md) | [directoryObject](directoryobject.md) collection | Retrieve a list of recently deleted applications. |
| [List deleted applications owned by user](../api/directory-deleteditems-user-owned.md) | [directoryObject](directoryobject.md) collection | Retrieve the applications deleted in the tenant in the last 30 days and that are owned by a user. |
|[Get deleted application](../api/directory-deleteditems-get.md) | [directoryObject](directoryobject.md) | Retrieve the properties of a recently deleted application. |
|[Permanently delete application](../api/directory-deleteditems-delete.md) | None | Permanently delete an applications. |
|[Restore deleted application](../api/directory-deleteditems-restore.md) | [directoryObject](directoryobject.md) | Restore a recently deleted application. |
|**Certificates and secrets**| | |
|[Add password](../api/application-addpassword.md)|[passwordCredential](passwordcredential.md)|Add a strong password to an application.|
|[Remove password](../api/application-removepassword.md)|[passwordCredential](passwordcredential.md)|Remove a password from an application.|
|[Add key](../api/application-addkey.md)|[keyCredential](keycredential.md)|Add a key credential to an application.|
|[Remove key](../api/application-removekey.md)|None|Remove a key credential from an application.|
|**Extensions**| | |
| [List extensionProperties](../api/application-list-extensionproperty.md) | [extensionProperty](extensionProperty.md) collection | List extension properties on an application object. |
| [Create extensionProperties](../api/application-post-extensionproperty.md) | [extensionProperty](extensionProperty.md) | Create an extension property on an application object. |
| [Get extensionProperty](../api/extensionproperty-delete.md) | None | Get an extension property from an application object. |
| [Delete extensionProperty](../api/extensionproperty-delete.md) | None | Delete an extension property from an application object. |
|[Get available extension properties](../api/directoryobject-getavailableextensionproperties.md)|[extensionProperty](../resources/extensionproperty.md) collection|Get all or a filtered list of the directory extension properties that have been registered in a directory.|
|**Owners**| | |
|[List owners](../api/application-list-owners.md) |[directoryObject](directoryobject.md) collection| Get an owner object collection.|
|[Add owner](../api/application-post-owners.md) |[directoryObject](directoryobject.md)| Add an owner by posting to the owners collection.|
|[Remove owner](../api/application-delete-owners.md) |None| Remove an owner from an application.|
|**Policies**| | |
|[Assign tokenIssuancePolicy](../api/application-post-tokenissuancepolicies.md)| [tokenIssuancePolicy](tokenissuancepolicy.md) collection| Assign a tokenIssuancePolicy to this object.|
|[List tokenIssuancePolicies](../api/application-list-tokenissuancepolicies.md)| [tokenIssuancePolicy](tokenissuancepolicy.md) collection| Get all tokenIssuancePolicies assigned to this object.|
|[Remove tokenIssuancePolicy](../api/application-delete-tokenissuancepolicies.md)| [tokenIssuancePolicy](tokenissuancepolicy.md) collection| Remove a tokenIssuancePolicy from this object.|
|[Assign tokenLifetimePolicy](../api/application-post-tokenlifetimepolicies.md)| [tokenLifetimePolicy](tokenlifetimepolicy.md) collection| Assign a tokenLifetimePolicy to this object.|
|[List tokenLifetimePolicies](../api/application-list-tokenlifetimepolicies.md)| [tokenLifetimePolicy](tokenlifetimepolicy.md) collection| Get all tokenLifetimePolicies assigned to this object.|
|[Remove tokenLifetimePolicy](../api/application-delete-tokenlifetimepolicies.md)| [tokenLifetimePolicy](tokenlifetimepolicy.md) collection| Remove a tokenLifetimePolicy from this object.|
|**Verified publisher**| | |
|[Set verified publisher](../api/application-setverifiedpublisher.md)| None | Set the verified publisher of an application.|
|[Unset verified publisher](../api/application-unsetverifiedpublisher.md)| None | Unset the verified publisher of an application.|

## Properties

> [!IMPORTANT]
> Specific usage of `$filter` and the `$search` query parameter is supported only when you use the **ConsistencyLevel** header set to `eventual` and `$count`. For more information, see [Advanced query capabilities on Azure AD directory objects](/graph/aad-advanced-queries#application-properties).

| Property | Type | Description |
|:---------------|:--------|:----------|
| addIns | [addIn](addin.md) collection| Defines custom behavior that a consuming service can use to call an app in specific contexts. For example, applications that can render file streams [may set the addIns property](/onedrive/developer/file-handlers) for its "FileHandler" functionality. This will let services like Office 365 call the application in the context of a document the user is working on. |
| api | [apiApplication](apiapplication.md) | Specifies settings for an application that implements a web API. |
| appId | String | The unique identifier for the application that is assigned to an application by Azure AD. Not nullable. Read-only. |
| applicationTemplateId | String | Unique identifier of the applicationTemplate. Supports `$filter` (`eq`, `not`, `ne`).|
| appRoles | [appRole](approle.md) collection | The collection of roles assigned to the application. With [app role assignments](approleassignment.md), these roles can be assigned to users, groups, or service principals associated with other applications. Not nullable. |
|certification|[certification](certification.md)|Specifies the certification status of the application.|
| createdDateTime | DateTimeOffset | The date and time the application was registered. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only. <br><br> Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`, and `eq` on `null` values) and `$orderBy`. |
| deletedDateTime | DateTimeOffset | The date and time the application was deleted. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only. |
| description | String | Free text field to provide a description of the application object to end users. The maximum allowed size is 1024 characters. Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `startsWith`) and `$search`. |
| disabledByMicrosoftStatus | String | Specifies whether Microsoft has disabled the registered application. Possible values are: `null` (default value), `NotDisabled`, and `DisabledDueToViolationOfServicesAgreement` (reasons may include suspicious, abusive, or malicious activity, or a violation of the Microsoft Services Agreement). <br><br> Supports `$filter` (`eq`, `ne`, `not`). |
| displayName | String | The display name for the application. Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`, `startsWith`, and `eq` on `null` values), `$search`, and `$orderBy`. |
| groupMembershipClaims | String | Configures the `groups` claim issued in a user or OAuth 2.0 access token that the application expects. To set this attribute, use one of the following valid string values: `None`, `SecurityGroup` (for security groups and Azure AD roles), `All` (this gets all of the security groups, distribution groups, and Azure AD directory roles that the signed-in user is a member of). |
| id | String | Unique identifier for the application object. This property is referred to as **Object ID** in the Azure portal. Inherited from [directoryObject](directoryobject.md). Key. Not nullable. Read-only. Supports `$filter` (`eq`, `ne`, `not`, `in`).|
| identifierUris | String collection | Also known as App ID URI, this value is set when an application is used as a resource app. The identifierUris acts as the prefix for the scopes you'll reference in your API's code, and it must be globally unique. You can use the default value provided, which is in the form `api://<application-client-id>`, or specify a more readable URI like `https://contoso.com/api`. For more information on valid identifierUris patterns and best practices, see [Azure AD application registration security best practices](/azure/active-directory/develop/security-best-practices-for-app-registration#appid-uri-configuration). Not nullable. <br><br>Supports `$filter` (`eq`, `ne`, `ge`, `le`, `startsWith`).|
| info | [informationalUrl](informationalurl.md) | Basic profile information of the application such as  app's marketing, support, terms of service and privacy statement URLs. The terms of service and privacy statement are surfaced to users through the user consent experience. For more info, see How to: [Add Terms of service and privacy statement for registered Azure AD apps](/azure/active-directory/develop/howto-add-terms-of-service-privacy-statement). <br><br>Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, and `eq` on `null` values). |
| isDeviceOnlyAuthSupported | Boolean | Specifies whether this application supports device authentication without a user. The default is `false`.  |
| isFallbackPublicClient | Boolean | Specifies the fallback application type as public client, such as an installed application running on a mobile device. The default value is `false` which means the fallback application type is confidential client such as a web app. There are certain scenarios where Azure AD cannot determine the client application type. For example, the [ROPC](https://tools.ietf.org/html/rfc6749#section-4.3) flow where it is configured without specifying a redirect URI. In those cases Azure AD interprets the application type based on the value of this property.|
| keyCredentials | [keyCredential](keycredential.md) collection | The collection of key credentials associated with the application. Not nullable. Supports `$filter` (`eq`, `not`, `ge`, `le`). |
| logo | Stream | The main logo for the application. Not nullable. |
| notes | String | Notes relevant for the management of the application. |
| oauth2RequiredPostResponse | Boolean | Specifies whether, as part of OAuth 2.0 token requests, Azure AD allows POST requests, as opposed to GET requests. The default is `false`, which specifies that only GET requests are allowed. |
| optionalClaims | [optionalClaims](optionalclaims.md) | Application developers can configure optional claims in their Azure AD applications to specify the claims that are sent to their application by the Microsoft security token service. For more information, see [How to: Provide optional claims to your app](/azure/active-directory/develop/active-directory-optional-claims).|
| parentalControlSettings | [parentalControlSettings](parentalcontrolsettings.md) |Specifies parental control settings for an application. |
| passwordCredentials | [passwordCredential](passwordcredential.md) collection|The collection of password credentials associated with the application. Not nullable.|
| publicClient | [publicClientApplication](publicclientapplication.md) | Specifies settings for installed clients such as desktop or mobile devices. |
| publisherDomain | String | The verified publisher domain for the application. Read-only. For more information, see [How to: Configure an application's publisher domain](/azure/active-directory/develop/howto-configure-publisher-domain). Supports `$filter` (`eq`, `ne`, `ge`, `le`, `startsWith`).|
| requiredResourceAccess |[requiredResourceAccess](requiredresourceaccess.md) collection| Specifies the resources that the application needs to access. This property also specifies the set of delegated permissions and application roles that it needs for each of those resources. This configuration of access to the required resources drives the consent experience. No more than 50 resource services (APIs) can be configured. Beginning mid-October 2021, the total number of required permissions must not exceed 400. Not nullable. <br><br>Supports `$filter` (`eq`, `not`, `ge`, `le`).|
| samlMetadataUrl | String | The URL where the service exposes SAML metadata for federation. This property is valid only for single-tenant applications. Nullable. |
| serviceManagementReference | String | References application or service contact information from a Service or Asset Management database. Nullable. |
| signInAudience | String | Specifies the Microsoft accounts that are supported for the current application. The possible values are: `AzureADMyOrg`, `AzureADMultipleOrgs`, `AzureADandPersonalMicrosoftAccount` (default), and `PersonalMicrosoftAccount`. See more in the [table below](#signinaudience-values). <br><br>Supports `$filter` (`eq`, `ne`, `not`).|
| spa                     | [spaApplication](../resources/spaapplication.md)                            | Specifies settings for a single-page application, including sign out URLs and redirect URIs for authorization codes and access tokens. |
| tags |String collection| Custom strings that can be used to categorize and identify the application. Not nullable. <br><br>Supports `$filter` (`eq`, `not`, `ge`, `le`, `startsWith`).|
| tokenEncryptionKeyId |String|Specifies the keyId of a public key from the keyCredentials collection. When configured, Azure AD encrypts all the tokens it emits by using the key this property points to. The application code that receives the encrypted token must use the matching private key to decrypt the token before it can be used for the signed-in user.|
| verifiedPublisher          | [verifiedPublisher](verifiedPublisher.md)                            | Specifies the verified publisher of the application. For more information about how publisher verification helps support application security, trustworthiness, and compliance, see [Publisher verification](/azure/active-directory/develop/publisher-verification-overview).|
| web |[webApplication](webapplication.md)| Specifies settings for a web application. |

### signInAudience values

| Value | Description |
|:---------------|:--------|
|AzureADMyOrg|Users with a Microsoft work or school account in my organization’s Azure AD tenant (single tenant).|
|AzureADMultipleOrgs|Users with a Microsoft work or school account in any organization’s Azure AD tenant (multi-tenant).|
|AzureADandPersonalMicrosoftAccount|Users with a personal Microsoft account, or a work or school account in any organization’s Azure AD tenant. For authenticating users with Azure AD B2C user flows, use `AzureADandPersonalMicrosoftAccount`. This value allows for the widest set of user identities including local accounts and user identities from Microsoft, Facebook, Google, Twitter, or any OpenID Connect provider. This is the default value for the **signInAudience** property. |
|PersonalMicrosoftAccount|Users with a personal Microsoft account only.|

## Relationships

| Relationship | Type | Description |
|:---------------|:--------|:----------|
|createdOnBehalfOf|[directoryObject](directoryobject.md)| Read-only.|
|extensionProperties|[extensionProperty](extensionproperty.md) collection| Read-only. Nullable. Supports `$expand` and `$filter` (`eq` when counting empty collections).|
|owners|[directoryObject](directoryobject.md) collection|Directory objects that are owners of the application. Read-only. Nullable. Supports `$expand`.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "keyProperty":"id",
  "optionalProperties": [
    "createdOnBehalfOf",
    "owners"
  ],
  "@odata.type": "microsoft.graph.application"
}-->

```json
{
  "addIns": [{"@odata.type": "microsoft.graph.addIn"}],
  "api": {"@odata.type": "microsoft.graph.apiApplication"},
  "appId": "String",
  "applicationTemplateId": "String",
  "appRoles": [{"@odata.type": "microsoft.graph.appRole"}],
  "certification": {"@odata.type": "microsoft.graph.certification"},
  "createdDateTime": "String (timestamp)",
  "deletedDateTime": "String (timestamp)",
  "disabledByMicrosoftStatus": "String",
  "displayName": "String",
  "groupMembershipClaims": "String",
  "id": "String (identifier)",
  "identifierUris": ["String"],
  "info": {"@odata.type": "microsoft.graph.informationalUrl"},
  "isDeviceOnlyAuthSupported": false,
  "isFallbackPublicClient": false,
  "keyCredentials": [{"@odata.type": "microsoft.graph.keyCredential"}],
  "logo": "Stream",
  "notes": "String",
  "oauth2RequiredPostResponse": false,
  "optionalClaims": {"@odata.type": "microsoft.graph.optionalClaims"},
  "parentalControlSettings": {"@odata.type": "microsoft.graph.parentalControlSettings"},
  "passwordCredentials": [{"@odata.type": "microsoft.graph.passwordCredential"}],
  "publicClient": {"@odata.type": "microsoft.graph.publicClientApplication"},
  "publisherDomain": "String",
  "requiredResourceAccess": [{"@odata.type": "microsoft.graph.requiredResourceAccess"}],
  "serviceManagementReference": "String",
  "signInAudience": "String",
  "spa": {"@odata.type": "microsoft.graph.spaApplication"},
  "tags": ["String"],
  "tokenEncryptionKeyId": "String",
  "verifiedPublisher": {"@odata.type": "microsoft.graph.verifiedPublisher"},
  "web": {"@odata.type": "microsoft.graph.webApplication"}
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "application resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
