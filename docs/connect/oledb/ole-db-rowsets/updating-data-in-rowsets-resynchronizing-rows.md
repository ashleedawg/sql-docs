---
title: "Resynchronizing Rows | Microsoft Docs"
description: "Resynchronizing rows using OLE DB Driver for SQL Server"
ms.custom: ""
ms.date: "03/26/2018"
ms.prod: "sql"
ms.prod_service: "database-engine, sql-database, sql-data-warehouse, pdw"
ms.service: ""
ms.component: "ole-db-rowsets"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "drivers"
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "synchronization [OLE DB]"
  - "IRowsetResynch interface"
  - "resynchronizing rows"
  - "data updates [SQL Server], OLE DB"
author: "pmasl"
ms.author: "Pedro.Lopes"
manager: craigg
---
# Updating Data in Rowsets - Resynchronizing Rows
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  The OLE DB Driver for SQL Server supports **IRowsetResynch** on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cursor-supported rowsets only. **IRowsetResynch** is not available on demand. The consumer must request the interface before opening the rowset.  
  
## See Also  
 [Updating Data in Rowsets](../../oledb/ole-db-rowsets/updating-data-in-rowsets.md)  
  
  
