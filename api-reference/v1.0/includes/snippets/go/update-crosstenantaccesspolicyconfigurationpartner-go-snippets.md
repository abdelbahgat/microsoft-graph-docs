---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewCrossTenantAccessPolicyConfigurationPartner()
inboundTrust := graphmodels.NewCrossTenantAccessPolicyInboundTrust()
isMfaAccepted := true
inboundTrust.SetIsMfaAccepted(&isMfaAccepted) 
isCompliantDeviceAccepted := true
inboundTrust.SetIsCompliantDeviceAccepted(&isCompliantDeviceAccepted) 
isHybridAzureADJoinedDeviceAccepted := true
inboundTrust.SetIsHybridAzureADJoinedDeviceAccepted(&isHybridAzureADJoinedDeviceAccepted) 
requestBody.SetInboundTrust(inboundTrust)

partners, err := graphClient.Policies().CrossTenantAccessPolicy().Partners().ByCrossTenantAccessPolicyConfigurationPartnerTenantId("crossTenantAccessPolicyConfigurationPartner-tenantId").Patch(context.Background(), requestBody, nil)


```