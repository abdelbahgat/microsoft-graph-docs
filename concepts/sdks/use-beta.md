---
title: "Use the Microsoft Graph SDKs with the beta API"
description: "Describes how use the Microsoft Graph SDKs with the beta version of the API."
ms.localizationpriority: medium
author: jasonjoh
---

# Use the Microsoft Graph SDKs with the beta API

Many of the Microsoft Graph SDKs use the [v1.0](/graph/api/overview?view=graph-rest-1.0&preserve-view=false) Microsoft Graph endpoint by default. The SDKs can be used with the [beta](/graph/api/overview?view=graph-rest-beta&preserve-view=true) endpoint for non-production applications. The method for accessing the beta endpoint depends on which SDK you are using.

[!INCLUDE [beta-disclaimer](../../api-reference/includes/beta-disclaimer.md)]

<!-- markdownlint-disable MD025 -->
# [C#](#tab/CS)

In order to call the beta API, you must install the [Microsoft.Graph.Beta](https://www.nuget.org/packages/Microsoft.Graph.Beta) package. Usage is the same as the `Microsoft.Graph` package.

```csharp
// Version 5.x
using Microsoft.Graph.Beta;
// Version 4.x and earlier
// using Microsoft.Graph;

// Create a new instance of GraphServiceClient.
GraphServiceClient graphClient = new GraphServiceClient(...);
```

# [TypeScript](#tab/typeScript)

The [Microsoft Graph JavaScript Client Library](https://github.com/microsoftgraph/msgraph-sdk-javascript) can call the beta API in one of two ways.

- You can set the version on the `MicrosoftGraph.Client` when you create it. All requests made by the client will go to the specified version.

    ```typescript
    const clientOptions: ClientOptions = {
      defaultVersion: 'beta',
      ...
    };

    // Initialize Graph client
    const client = MicrosoftGraph.Client.initWithMiddleware(clientOptions);
    ```

- You can set the version on a specific request by using the `version` function on the `GraphRequest` object.

    ```typescript
    const user = await client
      .api('/me')
      .version('beta')
      .get();
    ```

# [Java](#tab/Java)

In order to call the beta API, you must install the [Microsoft Graph Beta Java SDK](https://github.com/microsoftgraph/msgraph-beta-sdk-java). Usage is the same as the non-beta SDK.

```Java
GraphServiceClient graphClient = GraphServiceClient
    .builder()
    .authenticationProvider(authProvider)
    .buildClient();
```

# [Objective-C](#tab/Objective-C)

The [Microsoft Graph SDK for ObjC](https://github.com/microsoftgraph/msgraph-sdk-objc) requires you to build a URL string to the API you want to call. It provides a constant `MSGraphBaseURL` for the v1.0 endpoint. To use beta, you simply replace that with `https://graph.microsoft.com/beta`.

However, the models in the [Microsoft Graph Models SDK](https://github.com/microsoftgraph/msgraph-sdk-objc-models) are generated from objects in the v1.0 API, so they may not work with beta objects.

```objectivec
// GET /me
NSString* meUrlString = [NSString stringWithFormat:@"%@/me", "https://graph.microsoft.com/beta"];

NSURL* meUrl = [[NSURL alloc] initWithString:meUrlString];

NSMutableURLRequest* meRequest = [[NSMutableURLRequest alloc] initWithURL:meUrl];
```

# [PHP](#tab/PHP)

The [Microsoft Graph SDK for PHP](https://github.com/microsoftgraph/msgraph-sdk-php) supports the beta endpoint and models. You set the beta endpoint with the `setApiVersion` method. You will need to disambiguate the v1.0 and beta models by providing an alias.

```php
use Microsoft\Graph\Graph;
use Beta\Microsoft\Graph\Model as BetaModel;

class UseBeta
{
    public function run()
    {
        $accessToken = 'xxx';

        $graph = new Graph();
        $graph->setAccessToken($accessToken);

        $user = $graph->setApiVersion("beta")
                      ->createRequest("GET", "/me")
                      ->setReturnType(BetaModel\User::class)
                      ->execute();

        echo "Hello, I am $user->getGivenName() ";
    }
}
```

# [Go](#tab/Go)

[!INCLUDE [go-sdk-preview](../../includes/go-sdk-preview.md)]

In order to call the beta API, you must install the [Microsoft Graph Beta SDK for Go](https://github.com/microsoftgraph/msgraph-beta-sdk-go) package.

```go
import (
    msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
)
client := msgraphsdk.NewGraphServiceClientWithCredentials(credentials, scopes)
```

---


## See also
[SDKs in preview or GA status](sdks-overview.md#sdks-in-preview-or-ga-status).
