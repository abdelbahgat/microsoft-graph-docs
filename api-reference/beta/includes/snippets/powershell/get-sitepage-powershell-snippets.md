---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Sites

Get-MgSitePage -SiteId $siteId -SitePageId $sitePageId -Property "id,title" -ExpandProperty "webparts" 

```