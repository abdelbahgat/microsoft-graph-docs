---
title: "teamsAsyncOperationType enum type"
description: "Types of teamsAsyncOperation. Members are added here as more async operations are supported."
author: "nkramer"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: enumPageType
---

# teamsAsyncOperationType enum type

Namespace: microsoft.graph



Types of [teamsAsyncOperation](teamsasyncoperation.md). Members are added here as more async operations are supported.

## Members

| Member | Description |
|:---------------|:----------|
|invalid|Invalid value.|
|cloneTeam|Operation to clone a team.|
|archiveTeam|Operation to archive a team.|
|unarchiveTeam|Operation to restore an archived team.|
|createTeam|Operation to create a team from scratch.|
|unknownFutureValue| Evolvable enumeration sentinel value. Don't use. |
|teamifyGroup |Operation to create a team from a group. |
|createChannel |Operation to create a channel in a team. |
