---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc-beta device-management virtual-endpoint on-premises-connections patch --cloud-pc-on-premises-connection-id {cloudPcOnPremisesConnection-id} --body '{\
  "@odata.type": "#microsoft.graph.cloudPcOnPremisesConnection",\
  "displayName": "Display Name value",\
  "subscriptionId": "0ac520ee-14c0-480f-b6c9-0a90c585ffff",\
  "subscriptionName": "Subscription Name value",\
  "adDomainName": "Active Directory Domain Name value",\
  "adDomainUsername": "Active Directory Domain User Name value",\
  "organizationalUnit": "Organization Unit value",\
  "resourceGroupId": "/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c585ffff/resourceGroups/ExampleRG",\
  "virtualNetworkId": "/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c58ffff/resourceGroups/ExampleRG/providers/Microsoft.Network/virtualNetworks/ExampleVNet",\
  "subnetId": "/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c585ffff/resourceGroups/ExampleRG/providers/Microsoft.Network/virtualNetworks/ExampleVNet/subnets/default"\
}\
'

```