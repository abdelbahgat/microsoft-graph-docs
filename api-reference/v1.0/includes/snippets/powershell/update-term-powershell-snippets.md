---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Sites

$params = @{
	Labels = @(
		@{
			Name = "changedLabel"
			LanguageTag = "en-US"
			IsDefault = $true
		}
	)
}

Update-MgSiteTermStoreSetTerm -SiteId $siteId -SetId $setId -TermId $termId -BodyParameter $params

```