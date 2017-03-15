---
title: "CRowset::MovePrev | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset<TAccessor>.MovePrev"
  - "CRowset.MovePrev"
  - "MovePrev"
  - "CRowset::MovePrev"
  - "ATL.CRowset.MovePrev"
  - "ATL::CRowset<TAccessor>::MovePrev"
  - "ATL::CRowset::MovePrev"
  - "ATL.CRowset<TAccessor>.MovePrev"
  - "CRowset<TAccessor>::MovePrev"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MovePrev (méthode)"
ms.assetid: 7ced2bfb-f556-40fc-97ea-0d4e7213e114
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::MovePrev
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déplace le curseur vers l'enregistrement précédent.  
  
## Syntaxe  
  
```  
  
HRESULT MovePrev( ) throw( );  
  
```  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Cette méthode requiert que vous définissiez **DBPROP\_CANFETCHBACKWARDS** ou **DBPROP\_CANSCROLLBACKWARDS** sur `VARIANT_TRUE` avant d'appeler **Ouvrir** dans la table ou commande contenant l'ensemble de lignes.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)