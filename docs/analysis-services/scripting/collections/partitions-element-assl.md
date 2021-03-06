---
title: "Partitions Element (ASSL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/03/2017"
ms.prod: analysis-services
ms.prod_service: "analysis-services"
ms.service: ""
ms.component: ""
ms.reviewer: ""
ms.suite: "pro-bi"
ms.technology: 
  

ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: 
  - "Partitions Element"
apilocation: 
  - "http://schemas.microsoft.com/analysisservices/2003/engine"
apitype: "Schema"
applies_to: 
  - "SQL Server 2016 Preview"
f1_keywords: 
  - "Partitions"
helpviewer_keywords: 
  - "Partitions element"
ms.assetid: e41c97ca-da44-48e9-a454-d25ee74209fd
caps.latest.revision: 33
author: "Minewiskan"
ms.author: "owend"
manager: "kfile"
---
# Partitions Element (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  Contains the collection of [Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) elements used by a [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) element, or the collection of partition bindings that make up an out-of-line [MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md) element.  
  
## Syntax  
  
```xml  
  
<MeasureGroup> <!-- or MeasureGroupBinding -->  
   ...  
   <Partitions>  
      <Partition>...</Partition> <!-- parent: MeasureGroup -->  
      <!-- or -->  
      <Partition xsi:type="PartitionBinding">...</Partition> <!-- parent: MeasureGroupBinding -->  
   </Partitions>  
   ...  
</MeasureGroup>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md), [MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md)|  
|Child elements|See the table below.|  
  
|Ancestor or Parent|Child Element|  
|------------------------|-------------------|  
|[MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md)|[Partition](../../../analysis-services/scripting/objects/partition-element-assl.md)|  
|[MeasureGroupBinding](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md)|[Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) of type [PartitionBinding](../../../analysis-services/scripting/data-type/partitionbinding-data-type-assl.md)|  
  
## Remarks  
 The corresponding element in the Analysis Management Objects (AMO) object model is <xref:Microsoft.AnalysisServices.PartitionCollection>.  
  
## See Also  
 [Collections &#40;ASSL&#41;](../../../analysis-services/scripting/collections/collections-assl.md)  
  
  
