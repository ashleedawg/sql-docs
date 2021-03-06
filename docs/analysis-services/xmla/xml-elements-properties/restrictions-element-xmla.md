---
title: "Restrictions Element (XMLA) | Microsoft Docs"
ms.custom: ""
ms.date: "03/04/2017"
ms.prod: analysis-services
ms.prod_service: "analysis-services, azure-analysis-services"
ms.service: ""
ms.component: ""
ms.reviewer: ""
ms.suite: "pro-bi"
ms.technology: 
  

ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: 
  - "Restrictions Element"
apilocation: 
  - "http://schemas.microsoft.com/analysisservices/2003/engine"
apitype: "Schema"
applies_to: 
  - "SQL Server 2016 Preview"
f1_keywords: 
  - "urn:schemas-microsoft-com:xml-analysis#Restrictions"
  - "http://schemas.microsoft.com/analysisservices/2003/engine#Restrictions"
  - "microsoft.xml.analysis.restrictions"
helpviewer_keywords: 
  - "Restrictions element"
ms.assetid: e745ce13-b468-4372-a6f0-0da3d772dda3
caps.latest.revision: 11
author: "Minewiskan"
ms.author: "owend"
manager: "kfile"
---
# Restrictions Element (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Contains restriction columns and data used by the [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) method.  
  
## Syntax  
  
```  
  
<Discover>  
...  
   <Restrictions>  
      <RestrictionList>...</RestrictionList>  
   </Restrictions>  
...  
</Discover>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|None|  
|Default value|None|  
|Cardinality|1-1: Required element that occurs once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md)|  
|Child elements|[RestrictionList](../../../analysis-services/xmla/xml-elements-properties/restrictionlist-element-xmla.md)|  
  
## Remarks  
 The **Restrictions** element represents restriction columns and data used to restrict the information retrieved by the **Discover** method.  
  
## Example  
  
```  
<Discover xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <RequestType>DISCOVER_PROPERTIES</RequestType>  
   <Restrictions>  
      <RestrictionList xmlns="urn:schemas-microsoft-com:xml-analysis">  
         <PropertyName>Catalog</PropertyName>  
      </RestrictionList>  
   </Restrictions>  
   <Properties />  
</Discover>  
```  
  
## See Also  
 [Properties &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
