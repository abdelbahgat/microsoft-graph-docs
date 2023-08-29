---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewCloudPcOnPremisesConnection()
"@odata.type" := "#microsoft.graph.cloudPcOnPremisesConnection"
requestBody.Set"@odata.type"(&"@odata.type") 
displayName := "test-canary-02"
requestBody.SetDisplayName(&displayName) 
type := graphmodels.HYBRIDAZUREADJOIN_CLOUDPCONPREMISESCONNECTIONTYPE 
requestBody.SetType(&type) 
subscriptionId := "0ac520ee-14c0-480f-b6c9-0a90c585ffff"
requestBody.SetSubscriptionId(&subscriptionId) 
subscriptionName := "CPC customer 001 test subscription"
requestBody.SetSubscriptionName(&subscriptionName) 
adDomainName := "contoso001.com"
requestBody.SetAdDomainName(&adDomainName) 
adDomainUsername := "dcadmin"
requestBody.SetAdDomainUsername(&adDomainUsername) 
organizationalUnit := "OU=Domain Controllers, DC=contoso001, DC=com"
requestBody.SetOrganizationalUnit(&organizationalUnit) 
resourceGroupId := "/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c585ad47/resourceGroups/CustomerRG"
requestBody.SetResourceGroupId(&resourceGroupId) 
virtualNetworkId := "/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c585ad47/resourceGroups/CustomerRG/providers/Microsoft.Network/virtualNetworks/canary01-MyVNET"
requestBody.SetVirtualNetworkId(&virtualNetworkId) 
subnetId := "/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c585ad47/resourceGroups/CustomerRG/providers/Microsoft.Network/virtualNetworks/canary01-MyVNET/subnets/canary01-Subnet"
requestBody.SetSubnetId(&subnetId) 

result, err := graphClient.DeviceManagement().VirtualEndpoint().OnPremisesConnections().Post(requestBody)


```