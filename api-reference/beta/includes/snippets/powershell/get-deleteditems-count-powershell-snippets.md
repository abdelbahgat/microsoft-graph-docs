---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.DirectoryManagement

Get-MgDirectoryDeletedItem -DirectoryObjectId $directoryObjectId -CountVariable CountVar -Sort "deletedDateTime asc" -Property "id,displayName,deletedDateTime" 

```