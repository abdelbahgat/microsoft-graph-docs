---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Files

$params = @{
	comment = "Updating the latest guidelines"
}

Invoke-MgCheckinDriveItem -DriveId $driveId -DriveItemId $driveItemId -BodyParameter $params

```