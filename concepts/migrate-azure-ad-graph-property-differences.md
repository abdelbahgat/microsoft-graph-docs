---
title: "Property differences between Azure AD Graph and Microsoft Graph"
description: "Describes property differences between Azure AD Graph resources (entities) and Microsoft Graph, in order to help migrate apps accordingly."
author: "FaithOmbongi"
ms.author: ombongifaith
ms.reviewer: dkershaw
ms.localizationpriority: medium
ms.prod: "applications"
ms.date: 11/11/2022
---

# Property differences between Azure AD Graph and Microsoft Graph

This article is part of *step 1: review API differences* of the [process to migrate apps](migrate-azure-ad-graph-planning-checklist.md).

In general, the best way to compare the Azure Active Directory (Azure AD) Graph API to Microsoft Graph is to compare the underlying metadata for each service, especially the resource descriptions:

- [Azure AD Graph metadata](https://graph.windows.net/microsoft.com/$metadata?api-version=1.6)
- [Microsoft Graph beta metadata](https://graph.microsoft.com/beta/$metadata)
- [Microsoft Graph v1.0 metadata](https://graph.microsoft.com/v1.0/$metadata)

This article highlights property differences between resources. If a property isn't shown in this list, it's already available in the [v1.0 version](/graph/api/overview) of Microsoft Graph, with exactly the same name as in Azure AD Graph.

Because the [user](#user-property-differences) and [group](#group-property-differences) resources are so frequently used, they're listed first. Other resources are listed alphabetically.

## User property differences

The Azure AD Graph **User** resource inherits from **DirectoryObject**; it has been renamed to **user** in Microsoft Graph and inherits from **directoryObject**. 

The Microsoft Graph v1.0 endpoint returns a limited set of user properties by default, while Azure AD Graph returns all properties. To read other properties that aren't returned by default, specify them in a `$select` query. For more information, see the [user resource type](/graph/api/resources/user).

The following table lists the more property differences.

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br>property|Comments|
|---|---|---|
| **deletedTimestamp**| beta  &nbsp;-&nbsp; **deletedDateTime** <br> v1.0 &nbsp;-&nbsp; **deletedDateTime** | |
| **dirSyncEnabled** | beta &nbsp;-&nbsp;**onPremisesSyncEnabled** <br> v1.0 &nbsp;-&nbsp; **onPremisesSyncEnabled** | |
| **facsimileTelephoneNumber** | beta  &nbsp;-&nbsp; **faxNumber** <br> v1.0 &nbsp;-&nbsp; **faxNumber** | |
| **immutableId** | beta &nbsp;-&nbsp;**onPremisesImmutableId** <br> v1.0 &nbsp;-&nbsp; **onPremisesImmutableId**  | |
| **isCompromised** | beta  &nbsp;-&nbsp; _Not available_ <br> v1.0 &nbsp;-&nbsp; _Not available_ | The Microsoft Graph [identity protection](/graph/api/resources/identityprotection-root?view=graph-rest-beta&preserve-view=true) API provides more sophisticated functionality. |
| **lastDirSyncDateTime** | beta &nbsp;-&nbsp;**onPremisesLastSyncDateTime** <br> v1.0 &nbsp;-&nbsp; **onPremisesLastSyncDateTime** | |
| **mobile** | beta  &nbsp;-&nbsp; **mobilePhone** <br> v1.0 &nbsp;-&nbsp; **mobilePhone** | |
| **passwordProfile/enforceChangePasswordPolicy** | beta  &nbsp;-&nbsp; **passwordProfile/forceChangePasswordNextSignIn** <br> v1.0 &nbsp;-&nbsp; **passwordProfile/forceChangePasswordNextSignIn** | |
| **passwordProfile/forceChangePasswordNextLogin** | beta  &nbsp;-&nbsp; **passwordProfile/forceChangePasswordNextSignInWithMfa** <br> v1.0 &nbsp;-&nbsp; **passwordProfile/forceChangePasswordNextSignInWithMfa** | |
| **provisioningErrors** | beta &nbsp;-&nbsp; _Not available_ <br> v1.0 &nbsp;-&nbsp; _Not available_ | This property and its information are deprecated.  However, a new property describing any AD Connect related provisioning errors can be found in **onPremisesProvisioningErrors** |
| **refreshTokensValidFromDateTime** | beta&nbsp;-&nbsp;**signinSessionsValidFromDateTime**<br>v1.0&nbsp;-&nbsp;**signinSessionsValidFromDateTime** | |
| **signinNames** | beta &nbsp;-&nbsp; **identities/signInType** <br> v1.0 &nbsp;-&nbsp; **identities/signInType** | This property is now part of the [objectIdentity](/graph/api/resources/objectIdentity) resource.|
| **telephoneNumber** | beta  &nbsp;-&nbsp; **businessPhones** <br> v1.0 &nbsp;-&nbsp; **businessPhones** | |
| **thumbnailPhoto** | beta  &nbsp;-&nbsp; **photo**, photos <br> v1.0 &nbsp;-&nbsp; **photo**, photos | The Microsoft Entra thumbnail photo isn't available through Microsoft Graph.  Use the [photo API](/graph/api/resources/profilephoto) instead. |
| **userIdentities** | beta &nbsp;-&nbsp; **identities** <br> v1.0 &nbsp;-&nbsp; **identities** | See [objectIdentity](/graph/api/resources/objectIdentity) resource type for more details.|
| **userState** | beta  &nbsp;-&nbsp; **externalUserState** <br> v1.0 &nbsp;-&nbsp; **externalUserState** | |
| **userStateChangedOn** | beta&nbsp;-&nbsp;**externalUserStateChangeDateTime**<br>v1.0&nbsp;-&nbsp;**externalUserStateChangeDateTime** | |

## Group property differences

The Azure AD Graph **Group** resource inherits from **DirectoryObject**; it has been renamed to **group** in Microsoft Graph and inherits from **directoryObject**. Here are the property differences:

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **dirSyncEnabled** | beta &nbsp;-&nbsp;**onPremisesSyncEnabled** <br> v1.0 &nbsp;-&nbsp; **onPremisesSyncEnabled** | |
| **lastDirSyncDateTime** | beta&nbsp;-&nbsp;**onPremisesLastSyncDateTime**<br>v1.0&nbsp;-&nbsp;**onPremisesLastSyncDateTime** | |
| **provisioningErrors** | beta &nbsp;-&nbsp; _Not available_ <br> v1.0 &nbsp;-&nbsp; _Not available_ | This property and its information are deprecated.  However, a new property describing any AD Connect related provisioning errors can be found in **onPremisesProvisioningErrors** |

## Application property differences

The Azure AD Graph **Application** resource inherits from **DirectoryObject**; it has been renamed to **application** in Microsoft Graph and inherits from **directoryObject**. Here are the property differences:


| Azure AD Graph <br>(v1.6) property | Microsoft Graph<br> property                                                                                                                          | Comments                                                                                                                                                                                                                                                                                                                     |
|------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **acceptMappedClaims**             | beta &nbsp;-&nbsp;**api/acceptMappedClaims** <br> v1.0 &nbsp;-&nbsp; **api/acceptMappedClaims**                                                       | acceptMappedClaims are now part of the new api resource.                                                                                                                                                                                                                                                                      |
| **availableToOtherTenants**        | beta &nbsp;-&nbsp; **signInAudience** <br> v1.0 &nbsp;-&nbsp; **signInAudience**                                                                      | The default value for availableToOtherTenants is `false` (meaning `AzureADMyOrg`) while for signInAudience is `AzureADandPersonalMicrosoftAccount`.                                                                                                                                                                                                                                                                                                                              |
| **errorUrl**                       | beta &nbsp;-&nbsp;_not available_ <br> v1.0 &nbsp;-&nbsp;  _not available_                                                                            | This property is deprecated.                                                                                                                                                                                                                                                                                                 |
| **homepage**                       | beta &nbsp;-&nbsp;**web/homePageUrl** <br> v1.0 &nbsp;-&nbsp; **web/homePageUrl**                                                                     | homepage is now part of the new web resource.                                                                                                                                                                                                                                                                                |
| **informationalUrls**              | beta &nbsp;-&nbsp;**info** <br> v1.0 &nbsp;-&nbsp; **info**                                                                                           |                                                                                                                                                                                                                                                                                                                              |
| **knownClientApplications**        | beta&nbsp;-&nbsp;**api/knownClientApplications** <br> v1.0 &nbsp;-&nbsp;**api/knownClientApplications**                                               | knownClientApplications are now part of the new api resource.                                                                                                                                                                                                                                                                 |
| **logoutUrl**                      | beta &nbsp;-&nbsp;**web/logoutUrl** <br> v1.0 &nbsp;-&nbsp; **web/logoutUrl**                                                                         | logoutUrl is now part of the web resource.                                                                                                                                                                                                                                                                                   |
| **logoUrl**                        | beta &nbsp;-&nbsp;**info/logoUrl** <br> v1.0 &nbsp;-&nbsp; **info/logoUrl**                                                                           | logoUrl is now part of the new info resource.                                                                                                                                                                                                                                                                                |
| **mainLogo**                       | beta &nbsp;-&nbsp;**logo** <br> v1.0 &nbsp;-&nbsp;  **logo**                                                                                          |                                                                                                                                                                                                                                                                                                                              |
| **oauth2AllowIdTokenImplicitFlow** | beta&nbsp;-&nbsp;**web/implicitGrantSettings/enableIdTokenIssuance**<br>v1.0 &nbsp;-&nbsp;**web/implicitGrantSettings/enableIdTokenIssuance**         | Renamed, and now part of the new implicitGrantSettings resource.                                                                                                                                                                                                                                                             |
| **oauth2AllowImplicitFlow**        | beta&nbsp;-&nbsp;**web/implicitGrantSettings/enableAccessTokenIssuance**<br>v1.0 &nbsp;-&nbsp;**web/implicitGrantSettings/enableAccessTokenIssuance** | Renamed, and now part of the new implicitGrantSettings resource.                                                                                                                                                                                                                                                             |
| **oauth2AllowUrlPathMatching**     | beta &nbsp;-&nbsp;_not available_ <br> v1.0 &nbsp;-&nbsp;  _not available_                                                                            | This property is deprecated.                                                                                                                                                                                                                                                                                                 |
| **oauth2Permissions**              | beta&nbsp;-&nbsp;**api/oauth2PermissionScopes**<br> v1.0 &nbsp;-&nbsp;**api/oauth2PermissionScopes**                                                  | Renamed and now part of the new api resource.                                                                                                                                                                                                                                                                                |
| **publicClient**                   | beta &nbsp;-&nbsp; **isFallbackPublicClient** <br> v1.0 &nbsp;-&nbsp; **isFallbackPublicClient**                                                      | This property now has a new meaning &nbsp;-&nbsp; it contains the public client settings like redirectUris. Determining whether the app is a public or confidential client or not is now done automatically, with the isFallbackPublicClient property handling the one special case that can't be determined automatically. |
| **recordConsentConditions**        | beta &nbsp;-&nbsp;_not available_ <br> v1.0 &nbsp;-&nbsp;  _not available_                                                                            | This property is deprecated.                                                                                                                                                                                                                                                                                                 |
| **replyUrls**                      | beta&nbsp;-&nbsp;**web/redirectUris**, **publicClient/redirectUris**<br> v1.0 &nbsp;-&nbsp;**web/redirectUris**, **publicClient/redirectUris**        | And being renamed, redirectUris is now part of the new web and publicClient resources. This allows developers to use specific URIs for their web and public clients (such as an installed application on a desktop device).                                                                                           |
| **samlMetadataUrl**                | beta  &nbsp;-&nbsp; **samlMetadataUrl** <br> v1.0 &nbsp;-&nbsp; _Not yet available_                                                                  |                                                                                                                                                                                                                                                                                                                              |
| **serviceEndpoints**               | beta  &nbsp;-&nbsp; _Not available_  <br> v1.0 &nbsp;-&nbsp; _Not available_                                                                          | This property is deprecated, but is planned for servicePrincipal.                                                                                                                                                                                                                                                            |

## AppRoleAssignment differences

The Azure AD Graph **AppRoleAssignment** resource inherits from **DirectoryObject**; it has been renamed to **appRoleAssignment** in Microsoft Graph and inherits from **directoryObject**. Here are the property differences:


|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **creationTimestamp** | beta &nbsp;-&nbsp;**creationTimestamp** <br> v1.0 &nbsp;-&nbsp;**createdDateTime** | |
| **id** | beta &nbsp;-&nbsp;**appRoleId** <br> v1.0 &nbsp;-&nbsp;**appRoleId** | |

## Contact property differences

The Azure AD Graph **Contact** resource inherits from **DirectoryObject**; it has been renamed to **orgContact** in Microsoft Graph and inherits from **directoryObject**. Here are the property differences:

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **city** | beta&nbsp;-&nbsp;**addresse/city** <br> v1.0 &nbsp;-&nbsp; **addresses/city**  | The **city** property is part of the **addresses** resource collection. |
| **country** | beta&nbsp;-&nbsp;**addresses/countryOrRegion**<br> v1.0&nbsp;-&nbsp;**addresses/countryOrRegion**  | The **countryOrRegion** property is part of the **addresses** resource collection. |
| **dirSyncEnabled** | beta &nbsp;-&nbsp;**onPremisesSyncEnabled** <br> v1.0 &nbsp;-&nbsp;**onPremisesSyncEnabled**   | |
| **facsimileTelephoneNumber** | beta&nbsp;-&nbsp;**phones/businessFax** <br> v1.0 &nbsp;-&nbsp;**phones/businessFax** | Now part of the **phones** collection that supports various phone types. |
| **physicalDeliveryOfficeName** | beta &nbsp;-&nbsp;**officeLocation** <br> v1.0 &nbsp;-&nbsp; **officeLocation** | |
| **postalCode** | beta&nbsp;-&nbsp;**addresses/postalCode**<br> v1.0 &nbsp;-&nbsp;**addresses/postalCode** | The **postalCode** property is part of the **addresses** resource collection. |
| **provisioningErrors** | beta &nbsp;-&nbsp; not available <br> v1.0 &nbsp;-&nbsp; not available | This property and its information are deprecated.  However, a new property describing any AD Connect related provisioning errors can be found in **onPremisesProvisioningErrors**. Currently this is only available in `beta`. |
| **sipProxyAddress** |  beta &nbsp;-&nbsp;**imAddresses**<br> v1.0 &nbsp;-&nbsp;**imAddresses**  | |
| **state** | beta &nbsp;-&nbsp;**addresses/state**<br> v1.0 &nbsp;-&nbsp; **addresses/state**  | The **state** property is part of the **addresses** resource collection. |
| **streetAddress** | beta &nbsp;-&nbsp;**addresses/street**<br> v1.0 &nbsp;-&nbsp;**addresses/street**  | The **street** property is part of the **addresses** resource collection. |
| **telephoneNumber** | beta&nbsp;-&nbsp;**phones/business** <br> v1.0 &nbsp;-&nbsp;**phones/business** | Now part of the **phones** collection that supports various phone types. |
| **thumbnailPhoto** | beta &nbsp;-&nbsp;_Not&nbsp;yet&nbsp;available_&nbsp;<br> v1.0 &nbsp;-&nbsp; _Not yet available_ | |

## Contract property differences

The Azure AD Graph **Contract** resource inherits from **DirectoryObject**; it has been renamed to **contract** in Microsoft Graph and inherits from **directoryObject**. Here are the property differences:


|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **customerContextId** | beta &nbsp;-&nbsp;**customerId** <br> v1.0 &nbsp;-&nbsp; **customerId**  |  |

## Device property differences

The Azure AD Graph **Device** resource inherits from **DirectoryObject**; it has been renamed to **device** in Microsoft Graph and inherits from **directoryObject**. Here are the property differences:


|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **approximateLastLogonTimestamp** | beta&nbsp;-&nbsp;**approximateLastSignInDateTime** <br> v1.0 &nbsp;-&nbsp; **approximateLastSignInDateTime** |  |
| **complianceExpiryTime** | beta&nbsp;-&nbsp;**complianceExpirationDateTime** <br> v1.0 &nbsp;-&nbsp; **complianceExpirationDateTime** |  |
| **deviceObjectVersion** |  beta&nbsp;-&nbsp;**deviceVersion** <br> v1.0 &nbsp;-&nbsp; **deviceVersion** |  |
| **deviceOSType** | beta&nbsp;-&nbsp;**operatingSystem** <br> v1.0 &nbsp;-&nbsp; **operatingSystem** |  |
| **deviceOSVersion** | beta&nbsp;-&nbsp;**operatingSystemVersion** <br> v1.0 &nbsp;-&nbsp; **operatingSystemVersion** |  |
| **devicePhysicalIds** | beta&nbsp;-&nbsp;**physicalIds** <br> v1.0 &nbsp;-&nbsp; **physicalIds** |  |
| **deviceTrustType** | beta&nbsp;-&nbsp;**trustType** <br> v1.0 &nbsp;-&nbsp; **trustType** |  |
| **dirSyncEnabled** |  beta&nbsp;-&nbsp;**onPremisesSyncEnabled** <br> v1.0 &nbsp;-&nbsp; **onPremisesSyncEnabled** |  |
| **lastDirSyncTime** |  beta&nbsp;-&nbsp;**onPremisesLastSyncDateTime** <br> v1.0 &nbsp;-&nbsp; **onPremisesLastSyncDateTime** |  |

## DirectoryObject property differences

The Azure AD Graph **DirectoryObject** resource has been renamed to **directoryObject** in Microsoft Graph. The changes to its properties are seen in other resources that inherit from **DirectoryObject**. Here are the property differences:

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **deletionTimestamp** | beta&nbsp;-&nbsp;**deletedDateTime** <br> v1.0 &nbsp;-&nbsp; **deletedDateTime** | While **deletionTimestamp** was a DateTime type, **deletedDateTime** is a DateTimeOffset type.  |
| **objectId** | beta&nbsp;-&nbsp;**id** <br> v1.0 &nbsp;-&nbsp; **id** | The **id** property in Microsoft Graph is inherited from the [entity](/graph/api/resources/entity) resource. |
| **objectType** | beta&nbsp;-&nbsp;*Not available* <br> v1.0 &nbsp;-&nbsp; *Not available* | This property isn't used in Microsoft Graph. Instead, Microsoft Graph returns the **@odata.type** property but only for APIs that might return objects of different types or derived types. For example, the [List group members](/graph/api/group-list-members) API might return members who are [users](/graph/api/resources/user), [groups](/graph/api/resources/group), [service principals](/graph/api/resources/serviceprincipal), [organizational contacts](/graph/api/resources/orgcontact), or [devices](/graph/api/resources/device). For users, the **@odata.type** is `#microsoft.graph.user`. |

## DirectoryObjectReference property differences

The Azure AD Graph **DirectoryObjectReference** resource inherits from **DirectoryObject**; it has been renamed to **directoryObjectPartnerReference** in Microsoft Graph and inherits from **directoryObject**. Here are the property differences:

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **externalContextId** | beta&nbsp;-&nbsp;**externalPartnerTenantId** <br> v1.0 &nbsp;-&nbsp; **externalPartnerTenantId** |  |

## Domain property differences

The Azure AD Graph **Domain** resource has been renamed to **domain** in Microsoft Graph. Here are the property differences:

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **name** | beta&nbsp;-&nbsp;**id** <br> v1.0 &nbsp;-&nbsp; **id** | In Microsoft Graph, the unique identifier (ID) contains the domain name; the `name` property doesn't exist. |
| **forceDeleteState** |  beta&nbsp;-&nbsp;**state** <br> v1.0 &nbsp;-&nbsp; **state** | In Azure AD Graph, there are separate forceDelete and domain state properties.  In Microsoft Graph, all domain states are handled by the state property. |
| **isDefaultForCloudRedirections** | beta&nbsp;-&nbsp;_Not&nbsp;yet&nbsp;available_&nbsp;<br> v1.0 &nbsp;-&nbsp; _Not yet available_ | |

## OAuth2PermissionsGrant property differences

The Azure AD Graph **OAuth2PermissionsGrant** resource has been renamed to **oAuth2PermissionsGrant** in Microsoft Graph. Here are the property differences:

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **expiryTime** | beta&nbsp;-&nbsp;**expiryTime** <br> v1.0&nbsp;-&nbsp;_Removed_ | This property isn't used and is removed in Microsoft Graph v1.0. |
| **startTime** | beta&nbsp;-&nbsp;**startTime** <br> v1.0&nbsp;-&nbsp;_Removed_  | This property isn't used and is removed in Microsoft Graph v1.0. |

## Policy property differences

In Microsoft Graph, there are named policy types (such as **tokenIssuancePolicy** or **tokenLifetimePolicy**) rather than a generic policy resource type. More details are available in the [policy overview](/graph/api/resources/policy-overview).

## ServiceEndpoint property differences

The Azure AD Graph **ServiceEndpoint** resource inherits from **DirectoryObject**; it has been renamed to **endpoint** in Microsoft Graph and inherits from **directoryObject**. Here are the property differences:

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **serviceId** | beta&nbsp;-&nbsp;**providerId**<br> v1.0 &nbsp;-&nbsp;**providerId** | |
| **serviceName** | beta&nbsp;-&nbsp;**providerName**<br> v1.0 &nbsp;-&nbsp;**providerName** | |
| **resourceId** | beta&nbsp;-&nbsp;**providerResourceId**<br> v1.0 &nbsp;-&nbsp;**providerResourceId** | |

## ServicePrincipal property differences

The Azure AD Graph **ServicePrincipal** resource inherits from **DirectoryObject**; it has been renamed to **servicePrincipal** in Microsoft Graph and inherits from **directoryObject**. Here are the property differences:

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **appOwnerTenantId** | beta&nbsp;-&nbsp;**appOwnerOrganizationId** <br> v1.0 &nbsp;-&nbsp;**appOwnerOrganizationId** | Renamed. |
| **informationalUrls**| beta &nbsp;-&nbsp;**info** <br> v1.0 &nbsp;-&nbsp; **info** | |
| **oauth2Permissions** | beta  &nbsp;-&nbsp;**publishedPermissionScopes** <br> v1.0  &nbsp;-&nbsp;**oauth2PermissionScopes** | Renamed. |
| **preferredTokenSigningKeyEndDateTime** | beta&nbsp;-&nbsp;_Not yet available_ <br> v1.0 &nbsp;- _Not yet available_ | |
| **signInAudience** | beta&nbsp;-&nbsp;_Not yet available_ <br> v1.0 &nbsp;- _Not yet available_ | |
| **serviceEndpoints** | beta&nbsp;-&nbsp;**endpoint** <br> v1.0 &nbsp;-&nbsp;**endpoint** | Renamed. |

## TenantDetails property differences

The Azure AD Graph **TenantDetail** resource inherits from **DirectoryObject**; it has been renamed to **organization** in Microsoft Graph and inherits from **directoryObject**. Here are the property differences:

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **companyLastDirSyncTime** | beta&nbsp;-&nbsp;**onPremisesLastSyncDateTime** <br> v1.0&nbsp;-&nbsp;**onPremisesLastSyncDateTime** |  |
| **dirSyncEnabled** | beta&nbsp;-&nbsp;**onPremisesSyncEnabled** <br> v1.0 &nbsp;-&nbsp; **onPremisesSyncEnabled** |  |
| **provisioningErrors** | beta&nbsp;-&nbsp;_Not available_ <br> v1.0&nbsp;-&nbsp;_Not available_ | This property and its information are deprecated.|
| **telephoneNumber** | beta&nbsp;-&nbsp;**businessPhones** <br> v1.0&nbsp;-&nbsp;**businessPhones** |  |

## TrustedCasForPasswordlessAuth property differences

The Azure AD Graph **TrustedCasForPasswordlessAuth** resource has been renamed to [certificateBasedAuthConfiguration](/graph/api/resources/certificatebasedauthconfiguration). There are no property differences; however, there are differences in the **certificateAuthority** resource type used by the **certificateAuthorities** property.

### CertificateAuthorityInformation property differences

The Azure AD Graph **CertificateAuthorityInformation** has been renamed to **certificateAuthority** in Microsoft Graph. The following are the property differences.

|Azure AD Graph <br>(v1.6) property |Microsoft Graph<br> property|Comments|
|---|---|---|
| **authorityType** | beta&nbsp;-&nbsp;**isRootAuthority**<br> v1.0 &nbsp;-&nbsp;**isRootAuthority** | This property's type has also changed into a Boolean. Previously this property had to be set to either "RootAuthority" or "IntermediateAuthority". Setting the new property to **true** is equivalent to "RootAuthority". |
| **crlDistributionPoint** | beta&nbsp;-&nbsp;**certificateRevocationListUrl** <br> v1.0&nbsp;-&nbsp;**certificateRevocationListUrl** | |
| **deltaCrlDistributionPoint** | beta&nbsp;-&nbsp;**deltaCertificateRevocationListUrl** <br> v1.0&nbsp;-&nbsp;**deltaCertificateRevocationListUrl** | |
| **trustedCertificate** | beta&nbsp;-&nbsp;**certificate** <br> v1.0&nbsp;-&nbsp;**deltaCertificateRevocationListUrl** | |
| **trustedIssuer** | beta&nbsp;-&nbsp;**issuer**<br> v1.0&nbsp;-&nbsp;**issuer** | |
| **trustedIssuerSki** | beta&nbsp;-&nbsp;**issuerSki**<br> v1.0 &nbsp;-&nbsp;**issuerSki** | |

## Next Steps

- Learn about [method differences](migrate-azure-ad-graph-method-differences.md) between Azure AD Graph and Microsoft Graph.
- Review the [checklist](migrate-azure-ad-graph-planning-checklist.md) again.
