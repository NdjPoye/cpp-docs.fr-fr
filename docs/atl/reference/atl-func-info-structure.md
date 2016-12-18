---
title: "_ATL_FUNC_INFO Structure | Microsoft Docs"
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
  - "_ATL_FUNC_INFO"
  - "ATL::_ATL_FUNC_INFO"
  - "ATL._ATL_FUNC_INFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_FUNC_INFO structure"
  - "ATL_FUNC_INFO structure"
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_FUNC_INFO Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contient des informations de type utilisées pour décrire une méthode ou une propriété dans une dispinterface.  
  
## Syntaxe  
  
```  
  
      struct _ATL_FUNC_INFO{  
   CALLCONV cc;  
   VARTYPE vtReturn;  
   SHORT nParams;  
   VARTYPE pVarTypes[_ATL_MAX_VARTYPES];  
};  
```  
  
## Membres  
 **cc**  
 la convention d'appel ;  En utilisant cette structure avec la classe d' [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) , ce membre doit être **CC\_STDCALL**.  `CC_CDECL` est la seule option prise en charge dans Windows CE pour le champ d' `CALLCONV` de la structure d' `_ATL_FUNC_INFO` .  Toute autre valeur est donc pas prise en charge son comportement indéfini.  
  
 **vtReturn**  
 Le type variant de la valeur de retour de fonction.  
  
 **nParams**  
 Le nombre de paramètres de fonction.  
  
 **pVarTypes**  
 Un tableau de types variant des paramètres de fonction.  
  
## Notes  
 En interne, ATL utilise cette structure pour stocker les informations obtenues à partir d'une bibliothèque de types.  Vous devrez peut\-être manipuler cette structure directement si vous fournissez des informations de type pour un gestionnaire d'événements utilisé avec la classe d' [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) et la macro de [SINK\_ENTRY\_INFORMATION](../Topic/SINK_ENTRY_INFO.md) .  
  
## Exemple  
 À partir d'une méthode dispinterface définie dans IDL :  
  
 [!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/CPP/atl-func-info-structure_1.idl)]  
  
 vous définissez une structure d' `_ATL_FUNC_INFO` :  
  
 [!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/CPP/atl-func-info-structure_2.h)]  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl Class](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)