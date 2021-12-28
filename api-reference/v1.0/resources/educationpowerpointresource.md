---
title: "educationPowerPointResource resource type"
description: "A subclass of educationResource."
ms.localizationpriority: medium
author: "mmast-msft"
ms.prod: "education"
doc_type: resourcePageType
---

# educationPowerPointResource resource type

Namespace: microsoft.graph

A subclass of [educationResource](educationresource.md). 

This is a PowerPoint resource. The PowerPoint file must be uploaded in the **fileResource** directory associated with the 
assignment or submission.


## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|fileUrl|String|Location of the file on disk.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.educationPowerPointResource"
}-->

```json
{
  "fileUrl": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "educationPowerPointResource resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->

