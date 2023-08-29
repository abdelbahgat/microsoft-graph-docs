---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewInternalDomainFederation()
"@odata.type" := "#microsoft.graph.internalDomainFederation"
requestBody.Set"@odata.type"(&"@odata.type") 
displayName := "Contoso"
requestBody.SetDisplayName(&displayName) 
issuerUri := "http://contoso.com/adfs/services/trust"
requestBody.SetIssuerUri(&issuerUri) 
metadataExchangeUri := "https://sts.contoso.com/adfs/services/trust/mex"
requestBody.SetMetadataExchangeUri(&metadataExchangeUri) 
signingCertificate := "MIIE3jCCAsagAwIBAgIQQcyDaZz3MI"
requestBody.SetSigningCertificate(&signingCertificate) 
passiveSignInUri := "https://sts.contoso.com/adfs/ls"
requestBody.SetPassiveSignInUri(&passiveSignInUri) 
preferredAuthenticationProtocol := graphmodels.WSFED_AUTHENTICATIONPROTOCOL 
requestBody.SetPreferredAuthenticationProtocol(&preferredAuthenticationProtocol) 
activeSignInUri := "https://sts.contoso.com/adfs/services/trust/2005/usernamemixed"
requestBody.SetActiveSignInUri(&activeSignInUri) 
signOutUri := "https://sts.contoso.com/adfs/ls"
requestBody.SetSignOutUri(&signOutUri) 
promptLoginBehavior := graphmodels.NATIVESUPPORT_PROMPTLOGINBEHAVIOR 
requestBody.SetPromptLoginBehavior(&promptLoginBehavior) 
isSignedAuthenticationRequestRequired := true
requestBody.SetIsSignedAuthenticationRequestRequired(&isSignedAuthenticationRequestRequired) 
nextSigningCertificate := "MIIE3jCCAsagAwIBAgIQQcyDaZz3MI"
requestBody.SetNextSigningCertificate(&nextSigningCertificate) 
federatedIdpMfaBehavior := graphmodels.REJECTMFABYFEDERATEDIDP_FEDERATEDIDPMFABEHAVIOR 
requestBody.SetFederatedIdpMfaBehavior(&federatedIdpMfaBehavior) 

result, err := graphClient.DomainsById("domain-id").FederationConfiguration().Post(requestBody)


```