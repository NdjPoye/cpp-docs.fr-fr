---
title: "CAccessorRowset, classe | Microsoft Docs"
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
  - "CAccessorRowset"
  - "ATL.CAccessorRowset"
  - "ATL::CAccessorRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessorRowset (classe)"
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessorRowset, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsulates a rowset and its associated accessors in a single class.  
  
## Syntaxe  
  
```  
template <   
   class TAccessor = CNoAccessor,    
   template <typename T> class TRowset = CRowset    
>  
class CAccessorRowset :   
   public TAccessor,    
   public TRowset<TAccessor>  
```  
  
#### Paramètres  
 `TAccessor`  
 Un classe accesseur.  
  
 `TRowset`  
 Classes d'ensemble de lignes  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Bind](../../data/oledb/caccessorrowset-bind.md)|Crée des liaisons \(utilisées lorsque **bBind** est spécifié avec la valeur false dans [CCommand::Open](../../data/oledb/ccommand-open.md)\).|  
|[CAccessorRowset](../../data/oledb/caccessorrowset-caccessorrowset.md)|Constructeur.|  
|[Fermer](../../data/oledb/caccessorrowset-close.md)|Ferme l'ensemble de lignes et les accesseurs.|  
|[FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md)|Libère toutes les colonnes dans l'enregistrement actif qui doivent être libérées.|  
|[GetColumnInfo](../../data/oledb/caccessorrowset-getcolumninfo.md)|Implémente [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx).|  
  
## Notes  
 La classe `TAccessor` gère l'accesseur.  La classe *TRowset* gère l'ensemble de lignes.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)