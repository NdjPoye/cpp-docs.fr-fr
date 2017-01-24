---
title: "CTable, classe | Microsoft Docs"
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
  - "ATL::CTable"
  - "ATL.CTable"
  - "CTable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTable (classe)"
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTable, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit un moyen d'accéder directement à un ensemble de lignes unique \(un sans paramètre\).  
  
## Syntaxe  
  
```  
template <   
   class TAccessor = CNoAccessor,    
   template <typename T> class TRowset = CRowset    
>  
class CTable :    
   public CAccessorRowset <   
      TAccessor,    
      TRowset    
   >  
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
|[Ouvrez .](../../data/oledb/ctable-open.md)|Ouvre la table.|  
  
## Notes  
 Voir le [CCommand](../../data/oledb/ccommand-class.md) pour plus d'informations sur la façon d'exécuter une commande d'accéder à un ensemble de lignes.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx)