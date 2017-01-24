---
title: "CAutoPtrArray Class | Microsoft Docs"
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
  - "ATL::CAutoPtrArray<E>"
  - "CAutoPtrArray"
  - "ATL::CAutoPtrArray"
  - "ATL.CAutoPtrArray<E>"
  - "ATL.CAutoPtrArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtrArray class"
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoPtrArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes utiles lorsque vous construisez un tableau de pointeurs intelligents.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
typename E  
>  
class CAutoPtrArray : public CAtlArray<  
ATL::CAutoPtr< E>,  
CAutoPtrElementTraits< E>  
>  
```  
  
#### Paramètres  
 `E`  
 Le type pointeur.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAutoPtrArray::CAutoPtrArray](../Topic/CAutoPtrArray::CAutoPtrArray.md)|Constructeur.|  
  
## Notes  
 Cette classe fournit un constructeur et dérive des méthodes de [CAtlArray](../../atl/reference/catlarray-class.md) et de [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) pour faciliter la création d'un objet de classe de collection stockant les pointeurs intelligents.  
  
 Pour plus d'informations, consultez [Classes de collection ATL](../../atl/atl-collection-classes.md).  
  
## Hiérarchie d'héritage  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## Configuration requise  
 **Header:** atlcoll.h  
  
## Voir aussi  
 [CAtlArray Class](../../atl/reference/catlarray-class.md)   
 [CAutoPtrElementTraits Class](../../atl/reference/cautoptrelementtraits-class.md)   
 [CAutoPtrList Class](../../atl/reference/cautoptrlist-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)