---
title: "ISessionPropertiesImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ISessionPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISessionPropertiesImpl (classe)"
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ISessionPropertiesImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation de l'interface [ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx).  
  
## Syntaxe  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `ISessionPropertiesImpl`.  
  
 `PropClass`  
 Une classe de propriété définissable par l'utilisateur qui a par défaut `T`.  
  
## Membres  
  
### Méthodes d'interface  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)|Retourne la liste des propriétés du groupe de propriétés de session qui sont actuellement définies sur la session.|  
|[SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)|Définit les propriétés du groupe de propriétés de la session.|  
  
## Notes  
 Interface obligatoire sur les sessions.  Cette classe implémente les propriétés de session en appelant une fonction statique définie par [mappage de propriété](../../data/oledb/begin-propset-map.md).  Le mappage de propriété doit être spécifié dans votre classe session.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)