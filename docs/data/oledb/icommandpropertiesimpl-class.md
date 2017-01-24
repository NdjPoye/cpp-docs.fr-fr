---
title: "ICommandPropertiesImpl, classe | Microsoft Docs"
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
  - "ICommandPropertiesImpl"
  - "ATL.ICommandPropertiesImpl"
  - "ATL::ICommandPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandPropertiesImpl (classe)"
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandPropertiesImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation de l'interface [ICommandProperties](https://msdn.microsoft.com/en-us/library/ms723044.aspx).  
  
## Syntaxe  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de  
  
 `PropClass`  
 Votre classe de propriétés.  
  
## Membres  
  
### Methodes d'interface  
  
|||  
|-|-|  
|[ObtenirPropriétés](../../data/oledb/icommandpropertiesimpl-getproperties.md)|Rend la liste des propriétés qui sont actuellement demandés comme ensemble de lignes dans le groupe de propriétés Rowset .|  
|[SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)|Définit les propriétés du groupe de propriétés Rowset|  
  
## Notes  
 Ceci est obligatoire sur les commandes.  L'implémentation est fournie par une fonction statique définie par la macro [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)