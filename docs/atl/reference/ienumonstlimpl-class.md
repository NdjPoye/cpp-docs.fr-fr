---
title: "IEnumOnSTLImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IEnumOnSTLImpl"
  - "ATL.IEnumOnSTLImpl"
  - "ATL::IEnumOnSTLImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IEnumOnSTLImpl class"
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IEnumOnSTLImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe définit une interface d'énumérateur sur une collection STL.  
  
## Syntaxe  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class CollType  
>  
class ATL_NO_VTABLE IEnumOnSTLImpl :  
   public Base  
```  
  
#### Paramètres  
 `Base`  
 Une interface d'énumérateur COM \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\).  
  
 `piid`  
 Pointeur vers l'ID d'interface de l'interface d'énumérateur.  
  
 `T`  
 Le type d'élément exposé par l'interface d'énumérateur.  
  
 `Copy`  
 [classe de stratégie de copie](../../atl/atl-copy-policy-classes.md).  
  
 `CollType`  
 Une classe de conteneur STL.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IEnumOnSTLImpl::Clone](../Topic/IEnumOnSTLImpl::Clone.md)|L'implémentation de.|  
|[IEnumOnSTLImpl::Init](../Topic/IEnumOnSTLImpl::Init.md)|Initialise l'énumérateur.|  
|[IEnumOnSTLImpl::Next](../Topic/IEnumOnSTLImpl::Next.md)|L'implémentation de.|  
|[IEnumOnSTLImpl::Reset](../Topic/IEnumOnSTLImpl::Reset.md)|L'implémentation de.|  
|[IEnumOnSTLImpl::Skip](../Topic/IEnumOnSTLImpl::Skip.md)|L'implémentation de.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IEnumOnSTLImpl::m\_iter](../Topic/IEnumOnSTLImpl::m_iter.md)|L'itérateur qui représente la position actuelle de l'énumérateur dans la collection.|  
|[IEnumOnSTLImpl::m\_pcollection](../Topic/IEnumOnSTLImpl::m_pcollection.md)|Un pointeur au conteneur STL maintenant les éléments à énumérer.|  
|[IEnumOnSTLImpl::m\_spUnk](../Topic/IEnumOnSTLImpl::m_spUnk.md)|Le pointeur d' **IUnknown** de l'objet en fournissant la collection.|  
  
## Notes  
 `IEnumOnSTLImpl` fournit l'implémentation pour une interface d'énumérateur COM dans lequel les éléments sont énumérés sont stockés dans un conteneur STL\- compatible.  Cette classe est analogue à la classe de [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) , qui fournit une implémentation pour une interface d'énumérateur sur un tableau.  
  
> [!NOTE]
>  Consultez [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md) pour plus d'informations sur d'autres différences entre `CComEnumImpl` et `IEnumOnSTLImpl`.  
  
 En général, vous n'aurez pas besoin de créer votre propre classe d'énumérateur par dérivation de cette implémentation d'interface.  Si vous souhaitez utiliser un énumérateur ATL fourni en fonction d'un conteneur STL, il est plus courant pour créer une instance de [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), ou pour créer une classe de collection qui retourne un énumérateur par dérivation d' [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).  
  
 Toutefois, si vous devez fournir un énumérateur personnalisé \(par exemple, un exposant des interfaces en plus de l'interface d'énumérateur\), vous pouvez dériver de cette classe.  Dans ce cas il est probable que vous deviez substituer la méthode de [clone](../Topic/IEnumOnSTLImpl::Clone.md) pour fournir votre propre implémentation.  
  
## Hiérarchie d'héritage  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)