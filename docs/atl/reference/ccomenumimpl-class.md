---
title: "CComEnumImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComEnumImpl"
  - "ATL::CComEnumImpl"
  - "CComEnumImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnumImpl class"
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComEnumImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit l'implémentation pour une interface d'énumérateur COM dans lequel les éléments sont énumérés sont stockés dans un tableau.  
  
## Syntaxe  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy  
>  
class ATL_NO_VTABLE CComEnumImpl :   
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
 [classe de stratégie de copie](../../atl/atl-copy-policy-classes.md)homogène.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComEnumImpl::CComEnumImpl](../Topic/CComEnumImpl::CComEnumImpl.md)|Constructeur.|  
|[CComEnumImpl::~CComEnumImpl](../Topic/CComEnumImpl::~CComEnumImpl.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComEnumImpl::Clone](../Topic/CComEnumImpl::Clone.md)|L'implémentation de.|  
|[CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md)|Initialise l'énumérateur.|  
|[CComEnumImpl::Next](../Topic/CComEnumImpl::Next.md)|L'implémentation de.|  
|[CComEnumImpl::Reset](../Topic/CComEnumImpl::Reset.md)|L'implémentation de.|  
|[CComEnumImpl::Skip](../Topic/CComEnumImpl::Skip.md)|L'implémentation de.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComEnumImpl::m\_begin](../Topic/CComEnumImpl::m_begin.md)|Pointeur vers le premier élément du tableau.|  
|[CComEnumImpl::m\_dwFlags](../Topic/CComEnumImpl::m_dwFlags.md)|Indicateurs de copie passées via `Init`.|  
|[CComEnumImpl::m\_end](../Topic/CComEnumImpl::m_end.md)|Pointeur vers l'emplacement immédiatement au delà de le dernier élément du tableau.|  
|[CComEnumImpl::m\_iter](../Topic/CComEnumImpl::m_iter.md)|Un pointeur vers l'élément actuel dans le tableau.|  
|[CComEnumImpl::m\_spUnk](../Topic/CComEnumImpl::m_spUnk.md)|Le pointeur d' **IUnknown** de l'objet en fournissant la collection est énumérée.|  
  
## Notes  
 `CComEnumImpl` fournit l'implémentation pour une interface d'énumérateur COM dans lequel les éléments sont énumérés sont stockés dans un tableau.  Cette classe est analogue à la classe d' `IEnumOnSTLImpl` , qui fournit une implémentation d'une interface d'énumérateur sur un conteneur STL.  
  
> [!NOTE]
>  Pour plus d'informations sur d'autres différences entre `CComEnumImpl` et `IEnumOnSTLImpl`, consultez [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md).  
  
 En général, vous n'aurez pas besoin de créer votre propre classe d'énumérateur par dérivation de cette implémentation d'interface.  Si vous souhaitez utiliser un énumérateur ATL fourni en fonction d'un tableau, il est plus courant de créer une instance de [CComEnum](../../atl/reference/ccomenum-class.md).  
  
 Toutefois, si vous devez fournir un énumérateur personnalisé \(par exemple, un exposant des interfaces en plus de l'interface d'énumérateur\), vous pouvez dériver de cette classe.  Dans cette situation, il est probable que vous deviez substituer la méthode de [CComEnumImpl::Clone](../Topic/CComEnumImpl::Clone.md) pour fournir votre propre implémentation.  
  
 Pour plus d'informations, consultez [Collections et énumérateurs ATL](../../atl/atl-collections-and-enumerators.md).  
  
## Hiérarchie d'héritage  
 `Base`  
  
 `CComEnumImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [IEnumOnSTLImpl Class](../../atl/reference/ienumonstlimpl-class.md)   
 [CComEnum Class](../../atl/reference/ccomenum-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)