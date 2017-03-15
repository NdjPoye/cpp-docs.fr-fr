---
title: "CSimpleRow::Compare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSimpleRow.Compare"
  - "CSimpleRow::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare (méthode)"
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CSimpleRow::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare deux lignes pour voir si elles font référence à la même instance de ligne.  
  
## Syntaxe  
  
```  
  
      HRESULT Compare(   
   CSimpleRow* pRow    
);  
```  
  
#### Paramètres  
 `pRow`  
 Un pointeur vers un objet `CSimpleRow`.  
  
## Valeur de retour  
 Valeur de `HRESULT`, généralement `S_OK`, indiquant que les deux lignes sont la même instance de ligne, ou **S\_FALSE**, indiquant que les deux lignes sont différentes.  Voir le [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) dans *OLE DB guide de référence du programmeur* d'autres valeurs de retour possibles.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CSimpleRow, classe](../../data/oledb/csimplerow-class.md)   
 [CSimpleRow::ReleaseRow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)