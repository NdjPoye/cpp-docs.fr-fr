---
title: "CComQIPtrElementTraits Class | Microsoft Docs"
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
  - "ATL.CComQIPtrElementTraits"
  - "CComQIPtrElementTraits"
  - "ATL::CComQIPtrElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComQIPtrElementTraits class"
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComQIPtrElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes, des fonctions static, et les typedefs utiles pour créer des collections de pointeurs d'interface COM.  
  
## Syntaxe  
  
```  
  
      template<  
   typename I,  
   const IID* piid = & __uuidof( I )   
>   
class CComQIPtrElementTraits : public CDefaultElementTraits<  
   ATL::CComQIPtr< I, piid >  
>  
```  
  
#### Paramètres  
 `I`  
 Une interface COM qui spécifie le type de pointeur à enregistrer.  
  
 `piid`  
 Pointeur vers l'IID d' `I`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComQIPtrElementTraits::INARGTYPE](../Topic/CComQIPtrElementTraits::INARGTYPE.md)|Le type de données à utiliser pour ajouter des éléments à l'objet de classe de collection.|  
  
## Notes  
 Cette classe dérive des méthodes et fournit un typedef utile en créant une classe de collection du pointeur d'interface COM de [CComQIPtr](../../atl/reference/ccomqiptr-class.md) objets.  Cette classe est utilisée par les classes de [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) et de [CInterfaceList](../../atl/reference/cinterfacelist-class.md) .  
  
 Pour plus d'informations, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Hiérarchie d'héritage  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CComQIPtrElementTraits`  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)