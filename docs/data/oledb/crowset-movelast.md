---
title: "CRowset::MoveLast | Microsoft Docs"
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
  - "ATL::CRowset<TAccessor>::MoveLast"
  - "CRowset<TAccessor>::MoveLast"
  - "ATL.CRowset.MoveLast"
  - "ATL::CRowset::MoveLast"
  - "CRowset<TAccessor>.MoveLast"
  - "MoveLast"
  - "CRowset::MoveLast"
  - "ATL.CRowset<TAccessor>.MoveLast"
  - "CRowset.MoveLast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveLast (méthode)"
ms.assetid: 81063578-ae9d-467b-8c88-81d8fc66e020
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::MoveLast
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déplace le curseur sur la dernière ligne.  
  
## Syntaxe  
  
```  
  
HRESULT MoveLast( ) throw( );  
  
```  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Appelle [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) pour repositionner l'emplacement de NeXT\- FETCH à la dernière position et récupère la dernière ligne.  
  
 Cette méthode requiert que vous définissez **DBPROP\_CANSCROLLBACKWARDS** sur `VARIANT_TRUE` avant d'appeler **Open** sur la table ou la commande contenant l'ensemble de lignes. \(Pour de meilleures performances, vous pouvez également définir **DBPROP\_QUICKRESTART** sur `VARIANT_TRUE`.\)  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)