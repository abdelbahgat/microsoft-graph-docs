---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



policyRules, err := graphClient.NetworkAccess().ForwardingPolicies().ByForwardingPolicyId("forwardingPolicy-id").PolicyRules().ByPolicyRuleId("policyRule-id").Get(context.Background(), nil)


```