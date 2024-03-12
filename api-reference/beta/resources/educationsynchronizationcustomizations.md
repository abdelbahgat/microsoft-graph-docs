---
title: "educationSynchronizationCustomizations resource type"
description: "Contains the list of entities to sync and their customizations, if any."
ms.localizationpriority: medium
author: "mmast-msft"
ms.prod: "education"
doc_type: resourcePageType
---

# educationSynchronizationCustomizations resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Contains the list of entities to sync and their customizations, if any.

> [!NOTE]
> Customization of properties to sync does not apply to the Student Enrollments or  Teacher Rosters.

This resource is member of the following data providers:

- [educationCsvDataProvider](educationcsvdataprovider.md)
- [educationPowerSchoolDataProvider](educationpowerschooldataprovider.md)

## Properties

| Property          | Type                                    | Description                             |
| :---------------- | :-------------------------------------- | :-------------------------------------- |
| school            | [educationSynchronizationCustomization] | Customizations for School entities.     |
| section           | [educationSynchronizationCustomization] | Customizations for Section entities.    |
| student           | [educationSynchronizationCustomization] | Customizations for Student entities.    |
| teacher           | [educationSynchronizationCustomization] | Customizations for Teacher entities.    |
| studentEnrollment | [educationSynchronizationCustomization] | Customizations for Student Enrollments. |
| teacherRoster     | [educationSynchronizationCustomization] | Customizations for Teacher Rosters.     |

[educationsynchronizationcustomization]: educationsynchronizationcustomization.md

## JSON representation

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.educationSynchronizationCustomizations"
}-->

```json
{
  "school": {
    "@odata.type": "microsoft.graph.educationSynchronizationCustomization",
    "optionalPropertiesToSync": ["String"],
    "isSyncDeferred": "Boolean",
    "allowDisplayNameUpdate": "Boolean"
  },
  "section": {
    "@odata.type": "microsoft.graph.educationSynchronizationCustomization",
    "optionalPropertiesToSync": ["String"],
    "isSyncDeferred": "Boolean",
    "allowDisplayNameUpdate": "Boolean"
  },
  "student": {
    "@odata.type": "microsoft.graph.educationSynchronizationCustomization",
    "optionalPropertiesToSync": ["String"],
    "isSyncDeferred": "Boolean",
    "allowDisplayNameUpdate": "Boolean"
  },
  "teacher": {
    "@odata.type": "microsoft.graph.educationSynchronizationCustomization",
    "optionalPropertiesToSync": ["String"],
    "isSyncDeferred": "Boolean",
    "allowDisplayNameUpdate": "Boolean"
  },
  "studentEnrollment": {
    "@odata.type": "microsoft.graph.educationSynchronizationCustomization",
    "synchronizationStartDate": "DateTimeOffset",
    "isSyncDeferred": "Boolean",
    "allowDisplayNameUpdate": "Boolean"
  },
  "teacherRoster": {
    "@odata.type": "microsoft.graph.educationSynchronizationCustomization",
    "isSyncDeferred": "Boolean",
    "allowDisplayNameUpdate": "Boolean"
  }
}
```


