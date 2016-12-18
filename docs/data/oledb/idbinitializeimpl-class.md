---
title: "IDBInitializeImpl, classe | Microsoft Docs"
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
  - "ATL.IDBInitializeImpl<T>"
  - "ATL::IDBInitializeImpl<T>"
  - "IDBInitializeImpl"
  - "ATL::IDBInitializeImpl"
  - "ATL.IDBInitializeImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBInitializeImpl (classe)"
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBInitializeImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation de l'interface [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx).  
  
## Syntaxe  
  
```  
template <class T>  
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IDBInitializeImpl`.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[IDBInitializeImpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)|Constructeur.|  
  
### Méthodes d'interface  
  
|||  
|-|-|  
|[Initialize](../../data/oledb/idbinitializeimpl-initialize.md)|Démarre fournisseur.|  
|[Desinitialise](../../data/oledb/idbinitializeimpl-uninitialize.md)|Arrête le fournisseur.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_dwStatus](../../data/oledb/idbinitializeimpl-m-dwstatus.md)|Indicateurs de source de données.|  
|[m\_pCUtlPropInfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md)|Pointeur vers l'implémentation des informations de propriétés des bases de données croisées.|  
  
## Notes  
 Interface forcé sur les objets sources de données et interface facultative sur les énumérateurs.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)