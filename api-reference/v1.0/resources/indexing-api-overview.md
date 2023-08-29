---
title: "Use the Microsoft Search API to index data"
description: "Use Microsoft Graph to index custom items in the Microsoft Search service."
ms.localizationpriority: high
author: "snlraju-msft"
ms.prod: "search"
doc_type: conceptualPageType
---

# Use the Microsoft Search API to index data

You can use Microsoft Graph to add custom items to search results in the [Microsoft Search](/microsoftsearch/overview-microsoft-search) experience.

Requests to index data are performed on behalf of an application without the presence of a signed-in user, identified using an [access token with application permission](/graph/auth-v2-service).

## Common use cases

The use cases for the APIs in this section involve building [Microsoft Graph connectors](/microsoftsearch/connectors-overview), which involves the following primary steps:

1. [Create a connection](../api/externalconnectors-external-post-connections.md) to an external data source.
2. [Create and register a schema](../api/externalconnectors-schema-create.md) that describes the type and how to index the external data.
3. [Index the data](../api/externalconnectors-externalitem-create.md) as an external item.

| Use cases                                        | REST resources                              | See also |
|:-------------------------------------------------|:--------------------------------------------|:--|
| **Configuration actions**                        |                                             |   |
| Create, update, or delete a connection           | [externalConnection](externalconnectors-externalconnection.md) | [externalConnection methods](externalconnectors-externalconnection.md#methods) |
| Register a schema for the external data          | [schema](externalconnectors-schema.md)                         | [schema methods](externalconnectors-schema.md#methods) |
| **Indexing actions**                             |                                             |   |
| Add, update or delete a custom item in the index | [externalItem](externalconnectors-externalitem.md)             | [externalItem methods](externalconnectors-externalitem.md#methods) |

## Known limitations

The following are current known limitations:

- Organizations are limited to a maximum of 10 connections.
- You can create only four `externalItem` resources items per second.
- An application is limited to four concurrent operations on a connection.
- Connections have a capacity limit of 5,000,000 items or ~350 GB of data.
- Maximum size of an `externalItem` entity is 4 MB.
- Sorting results is not supported.

## What's new
Find out about the [latest new features and updates](/graph/whats-new-overview) for this API set.

## Next steps

- See the [Microsoft Search API overview](/graph/search-concept-overview).
- Drill down on the methods, properties, and relationships of the [externalConnection](externalconnectors-externalconnection.md), [schema](externalconnectors-schema.md), and [externalItem](externalconnectors-externalitem.md) resources.
- Check out the [Microsoft Graph postman collection](https://www.postman.com/microsoftgraph/workspace/microsoft-graph/folder/455214-66cbb476-ad94-448e-ba5a-ef58e1da7a90?ctx=documentation) ([learn more](https://developer.microsoft.com/en-us/graph/blogs/postman-collections))
- Check out the [sample search connector](https://github.com/microsoftgraph/msgraph-search-connector-sample) from GitHub.


