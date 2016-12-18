---
title: "CInterfaceArray Class | Microsoft Docs"
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
  - "ATL.CInterfaceArray"
  - "CInterfaceArray"
  - "ATL::CInterfaceArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterfaceArray class"
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CInterfaceArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes utiles lorsque vous construisez un tableau de pointeurs d'interface COM.  
  
## Syntaxe  
  
```  
  
      template<  
   class I,  
   const IID* piid = & __uuidof( I )  
>  
class CInterfaceArray : public CAtlArray<  
   ATL::CComQIPtr< I, piid >,  
   CComQIPtrElementTraits< I, piid >  
>  
```  
  
#### Paramètres  
 `I`  
 Une interface COM qui spécifie le type de pointeur à enregistrer.  
  
 `piid`  
 Pointeur vers l'IID d' `I`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CInterfaceArray::CInterfaceArray](../Topic/CInterfaceArray::CInterfaceArray.md)|Le constructeur de tableau d'interface.|  
  
## Notes  
 Cette classe fournit un constructeur et des méthodes dérivées pour créer un tableau de pointeurs d'interface COM.  Utilisation [CInterfaceList](../../atl/reference/cinterfacelist-class.md) lorsque la liste est requise.  
  
 Pour plus d'informations, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Hiérarchie d'héritage  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CAtlArray Class](../../atl/reference/catlarray-class.md)   
 [CComQIPtr Class](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits Class](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)