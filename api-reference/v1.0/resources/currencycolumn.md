---
author: JeremyKelley
ms.date: 09/11/2017
title: CurrencyColumn
ms.localizationpriority: medium
description: "The currencyColumn on a columnDefinition resource indicates that the column's values represent currency."
ms.prod: sites-and-lists
doc_type: resourcePageType
---

# CurrencyColumn resource type

Namespace: microsoft.graph

The **currencyColumn** on a [columnDefinition](columndefinition.md) resource indicates that the column's values represent currency.

## JSON representation

Here is a JSON representation of a **currencyColumn** resource.
<!-- { "blockType": "resource", "@odata.type": "microsoft.graph.currencyColumn" } -->

```json
{
  "locale": "en-us"
}
```

## Properties

| Property name | Type   | Description
|:--------------|:-------|:----------------------------------------------------
| **locale**    | string | Specifies the locale from which to infer the currency symbol.

<!-- {
  "type": "#page.annotation",
  "description": "",
  "keywords": "",
  "section": "documentation",
  "tocPath": "Resources/CurrencyColumn"
} -->

