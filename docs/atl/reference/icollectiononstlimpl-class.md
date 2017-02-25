---
title: "ICollectionOnSTLImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.ICollectionOnSTLImpl"
  - "ATL::ICollectionOnSTLImpl"
  - "ICollectionOnSTLImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICollectionOnSTLImpl class"
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# ICollectionOnSTLImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes utilisées par une classe de collection.  
  
## Syntaxe  
  
```  
  
      template <  
   class T,  
   class CollType,  
   class ItemType,  
   class CopyItem,  
   class EnumType  
>  
class ICollectionOnSTLImpl :  
   public T  
```  
  
#### Paramètres  
 `T`  
 Une interface de la collection de COM.  
  
 `CollType`  
 Une classe de conteneur STL.  
  
 *itemType*  
 Le type d'élément exposé par l'interface du conteneur.  
  
 *CopyItem*  
 [classe de stratégie de copie](../../atl/atl-copy-policy-classes.md).  
  
 *EnumType*  
 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)\- classe compatible d'énumérateur.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ICollectionOnSTLImpl::get\_\_NewEnum](../Topic/ICollectionOnSTLImpl::get__NewEnum.md)|Retourne un objet énumérateur pour la collection.|  
|[ICollectionOnSTLImpl::get\_Count](../Topic/ICollectionOnSTLImpl::get_Count.md)|Retourne le nombre d'éléments dans la collection.|  
|[ICollectionOnSTLImpl::get\_Item](../Topic/ICollectionOnSTLImpl::get_Item.md)|Retourne l'élément demandé de la collection.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[ICollectionOnSTLImpl::m\_coll](../Topic/ICollectionOnSTLImpl::m_coll.md)|Collection.|  
  
## Notes  
 Cette classe fournit l'implémentation pour trois méthodes d'interface de la collection : [get\_Count](../Topic/ICollectionOnSTLImpl::get_Count.md), [get\_Item](../Topic/ICollectionOnSTLImpl::get_Item.md), et [get\_\_NewEnum](../Topic/ICollectionOnSTLImpl::get__NewEnum.md).  
  
 Pour utiliser cette classe :  
  
-   Définissez \(ou emprunt\) une interface de la collection que vous souhaitez à implémenter.  
  
-   Dérivez votre classe d'une spécialisation d' `ICollectionOnSTLImpl` sur cette interface de la collection.  
  
-   Utilisez votre classe dérivée pour implémenter toutes les méthodes de l'interface de la collection n'est pas gérée par `ICollectionOnSTLImpl`.  
  
> [!NOTE]
>  Si l'interface de la collection est une interface double, dérivez votre classe d' [IDispatchImpl](../../atl/reference/idispatchimpl-class.md), en passant la spécialisation d' `ICollectionOnSTLImpl` comme premier paramètre de modèle si vous souhaitez ATL pour fournir l'implémentation des méthodes d' `IDispatch` .  
  
-   Ajoutez des éléments au membre de [m\_coll](../Topic/ICollectionOnSTLImpl::m_coll.md) pour remplir une collection.  
  
 Pour plus d'informations et d'exemples, consultez [Collections et énumérateurs ATL](../../atl/atl-collections-and-enumerators.md).  
  
## Hiérarchie d'héritage  
 `T`  
  
 `ICollectionOnSTLImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [ATLCollections](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)