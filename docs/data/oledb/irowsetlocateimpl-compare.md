---
title: "IRowsetLocateImpl::Compare | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetLocateImpl.Compare"
  - "IRowsetLocateImpl::Compare"
  - "IRowsetLocateImpl.Compare"
  - "ATL::IRowsetLocateImpl::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare (méthode)"
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetLocateImpl::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare deux signets.  
  
## Syntaxe  
  
```  
  
      STDMETHOD ( Compare )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison   
);  
```  
  
#### Paramètres  
 Consultez [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx) dans le *OLE DB Programmer's Reference*.  
  
## Notes  
 L'une des signets peut être [signet standard](https://msdn.microsoft.com/en-us/library/ms712954.aspx) Bibliothèque de bases de données défini par OLE standard \(**DBBMK\_FIRST**, **DBBMK\_LAST**, ou **DBBMK\_INVALID**\).  La valeur retournée dans `pComparison` montre la relation entre les deux signets :  
  
-   **DBCOMPARE\_LT** \(`cbBookmark1` est\-à\-dire avant `cbBookmark2`.\)  
  
-   **DBCOMPARE\_EQ** \(`cbBookmark1` est égal à `cbBookmark2`.\)  
  
-   **DBCOMPARE\_GT** \(`cbBookmark1` est une `cbBookmark2`.\)  
  
-   **DBCOMPARE\_NE** \(les signets sont égaux et non ordonnés.\)  
  
-   **DBCOMPARE\_NOTCOMPARABLE** \(les signets ne peuvent pas être comparés.\)  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetLocateImpl, classe](../../data/oledb/irowsetlocateimpl-class.md)