---
title: "IOpenRowsetImpl, classe | Microsoft Docs"
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
  - "IOpenRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IOpenRowsetImpl (classe)"
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IOpenRowsetImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation pour l'interface `IOpenRowset`.  
  
## Syntaxe  
  
```  
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### Paramètres  
 `SessionClass`  
 Votre classe, dérivée de `IOpenRowsetImpl`.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|Crée un objet d'un ensemble de lignes.  Pas appelé directement par l'utilisateur.|  
|[OpenRowset](../../data/oledb/iopenrowsetimpl-openrowset.md)|Ouvre et retourne un ensemble de lignes qui inclut toutes les lignes d'une table de base ou d'index. \(Pas dans ATLDB.H\)|  
  
## Notes  
 L'interface de [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx) est obligatoire pour un objet session.  Cela ouvre et retourne un ensemble de lignes qui inclut toutes les lignes d'une table de base ou d'index.  
  
## Configuration requise  
 **En\-tête:** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)