---
title: "CArrayRowset, classe | Microsoft Docs"
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
  - "ATL.CArrayRowset<TAccessor>"
  - "ATL.CArrayRowset"
  - "CArrayRowset"
  - "ATL::CArrayRowset"
  - "ATL::CArrayRowset<TAccessor>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArrayRowset (classe)"
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArrayRowset, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Accède aux éléments d'un ensemble de lignes à l'aide de la syntaxe de table.  
  
## Syntaxe  
  
```  
template < class TAccessor >  
class CArrayRowset :   
   public CVirtualBuffer <TAccessor>,   
   protected CBulkRowset <TAccessor>  
```  
  
#### Paramètres  
 `TAccessor`  
 Type de classe d'accesseur que vous souhaitez que l'ensemble de lignes utilise.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CArrayRowset](../../data/oledb/carrayrowset-carrayrowset.md)|Constructeur.|  
|[Instantané](../../data/oledb/carrayrowset-snapshot.md)|Lit l'ensemble de lignes entier en mémoire.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[Operator&#91;&#93;](../../data/oledb/carrayrowset-operator.md)|Accède à un élément de l'ensemble de lignes.|  
  
### Membres de données  
  
|||  
|-|-|  
|[CArrayRowset::m\_nRowsRead](../../data/oledb/carrayrowset-m-nrowsread.md)|Le nombre de lignes affiche déjà.|  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CRowset, classe](../../data/oledb/crowset-class.md)